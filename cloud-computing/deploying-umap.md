---
title: Deploying uMap
# change to date to last-modified after next modification
date: 2025-03-13
---

[uMap](https://umap-project.org/){target="\_blank"} is an
[OpenStreetMap (OSM)](https://www.openstreetmap.org/about){target="\_blank"}
project that provides a free and open-source web mapping tool. Researchers with
access to a uMap instance can quickly create, manage, and share web maps with
their own data using a comprehensive set of editing tools or via imported data
from OSM or a local GeoJSON file.

This page provides a tutorial on how to deploy a uMap instance to an Alliance
Cloud virtual machine (VM), and it's been adapted from the
[uMap Documentation](https://docs.umap-project.org/en/stable/){target="\_blank"}.
The deployment process is relatively technical and has the following
requirements:

- Status as faculty or a librarian with an institution that holds eligibility
  for CFI grants
- Working knowledge of UNIX/Linux
- A domain name

Hosting a uMap instance on an Alliance Cloud VM provides additional flexibility
and more control to ensure stability, but multiple open uMap instances are
available and provide users the ability to freely register and create maps on a
hosted service. OSM's Wiki provides a listing of instances
[here](https://wiki.openstreetmap.org/wiki/UMap#Instances){target="\_blank"}
with <https://umap.openstreetmap.fr/en/>{target="\_blank"} being the most
popular option.

## Installation

1. Canada-based faculty can access cloud computing resources through the
   Alliance Cloud. The best-suited resource for running an ongoing service is a
   [persistent virtual machine](https://ubc-geography.github.io/computing-resources/cloud-computing/#persistent-instances){target="\_blank"},
   which acts as a virtual private server.
   [Create an account](https://alliancecan.ca/en/services/advanced-research-computing/account-management/apply-account){target="\_blank"}
   with Alliance (if you haven't already done so) and submit a
   [Rapid Access Service request (RAS)](https://docs.google.com/forms/d/e/1FAIpQLSeU_BoRk5cEz3AvVLf3e9yZJq-OvcFCQ-mg7p4AWXmUkd5rTw/viewform){target="\_blank"}
   with the number of resources that you anticipate using. The following
   resource recommendations should accommodate the needs of most uMap instances,
   but you should request more if you anticipate heavy traffic or higher storage
   needs.

   - vCPU: 1
   - Instances: 1
   - Volumes: 1
   - Volume snapshots: 0
   - RAM: 1.5
   - Floating IPs: 1
   - Persistent storage: 20
   - Object storage: 0
   - Shared filesystem storage: 0

::: {.callout-note}

The recommendations above provides 20 GB of storage in total to your VM. You can
anticipate that about 2.5 GB will be reserved for the Linux OS, leaving you with
17.5 GB of storage for uMap's static assets and user developed data layers.
Adjust your request for persistent storage as needed. If you plan on using more
than 50 GB of storage, consider including
[object storage](https://ubc-geography.github.io/computing-resources/cloud-computing/object-storage.html){target="\_blank"}
in your request and using that for as your data storage location. See
[uMap's documentation](https://docs.umap-project.org/en/stable/config/storage/){target="\_blank"}
for more details.

:::

1. Once your request has been approved, the Alliance Cloud team will provide you
   with access to an OpenStack dashboard, where you'll be able to manage your
   allocated cloud resources. Follow the Alliance's
   [Cloud Quick Start](https://docs.alliancecan.ca/wiki/Cloud_Quick_Start){target="\_blank"}
   guide to set up an SSH key pair (if you haven't already generated one) and
   launch a persistent virtual machine. We recommend using the Debian image as
   your boot source. You should also review
   [security considerations with running a VM](https://docs.alliancecan.ca/wiki/Security_considerations_when_running_a_VM){target="\_blank"}.

2. You should now have SSH access to your virtual machine, and you can start
   installing uMap's system dependencies, python, postgresql, and postgis.

   ```bash
   sudo apt-get update
   sudo apt install python3 python3-dev python3-venv virtualenv postgresql gcc postgis libpq-dev
   ```

3. Temporarily switch to the postgres user to add the umap user to postgresql,
   create a new database, and add the postgis extension.

   ```bash
   sudo su - postgres
   createuser umap
   createdb umap -O umap
   psql umap -c "CREATE EXTENSION postgis"
   exit
   ```

4. Add a new user named umap to your virtual machine and only provide the user
   with the necessary privileges to run uMap. Download a starter config file for
   your uMap instance and update it with a new and unique secret key.

   ```bash
   sudo adduser umap --disabled-password
   sudo mkdir -p /etc/umap /srv/umap/static /srv/umap/data
   sudo wget https://raw.githubusercontent.com/umap-project/umap/master/umap/settings/local.py.sample -O umap.conf
   sudo sed -i "s/\!\!change me\!\!/$(openssl rand -base64 32)/" umap.conf
   sudo chown umap:umap /srv/umap
   ```

5. You'll likely want to make a range of modifications to the local_settings.py
   file, but to get uMap running, you'll need to make the following
   modifications:

   ```bash
   sudo nano /etc/umap/umap.conf
   ```

   ```{.sh filename="/etc/umap/umap.conf"}
   ...
   DATABASES = {
       "default": {
           "ENGINE": "django.contrib.gis.db.backends.postgis",
           "NAME": "umap",
           "USER": "umap",
       }
   }
   ...
   ```

6. Switch to the umap user and run the commands in the following steps as that
   user.

   ```bash
   sudo su - umap
   ```

7. uMap has been developed using Python and the Django web framework, so it can
   be easily installed using a virtual environment and `pip`. An additional
   package, gunicorn, is also included. This package will be used to deploy uMap
   through a production-ready server.

   ```bash
   python3 -m venv venv
   source venv/bin/activate
   (venv) python3 -m pip install umap-project gunicorn
   deactivate
   ```

8. Use the following commands to create the necessary tables in the umap
   database, collect static assets for uMap's frontend, and create your
   administrator account. And enter `exit` to return to your default Debian
   user.

   ```bash
   umap migrate
   umap collectstatic
   umap createsuperuser
   exit
   ```

9. uMap requires a Web Server Gateway Interface (WSGI) for it to be effectively
   deployed, and Gunicorn is a popular WSGI server that works well with uMap.
   The following commands deploy uMap through
   [a systemd service and a UNIX socket running Gunicorn](https://docs.gunicorn.org/en/latest/deploy.html#systemd){target="\_blank"}.
   This provides some added stability to the instance by ensuring it starts
   whenever the system restarts.

   ```bash
   sudo nano /etc/systemd/system/umap.service
   ```

   ```{.sh filename="/etc/systemd/system/umap.service"}
   [Unit]
   Description=umap daemon
   Requires=umap.socket
   After=network.target

   [Service]
   Type=notify
   NotifyAccess=main
   User=umap
   Group=umap
   RuntimeDirectory=gunicorn
   WorkingDirectory=/srv/umap/
   ExecStart=/home/umap/venv/bin/gunicorn -w 3 umap.wsgi
   ExecReload=/bin/kill -s HUP $MAINPID
   KillMode=mixed
   TimeoutStopSec=5
   PrivateTmp=true
   EnvironmentFile=/srv/umap/env
   RestartSec=1
   Restart=always
   ProtectSystem=strict
   ReadWritePaths=/srv/umap/var/data

   [Install]
   WantedBy=multi-user.target
   ```

   ```bash
   sudo nano /etc/systemd/system/umap.socket
   ```

   ```{.sh filename="/etc/systemd/system/umap.socket"}
   [Unit]
   Description=umap socket
   Requires=postgresql.service

   [Socket]
   ListenStream=/run/umap.sock
   SocketUser=caddy
   SocketGroup=caddy
   SocketMode=0660

   [Install]
   WantedBy=sockets.target
   ```

   ```bash
   sudo systemctl daemon-reload
   sudo systemctl enable --now umap.socket
   ```

10. Through your domain name registrar, create a DNS A record that points your
    domain name or subdomain to your VM’s floating IP address. Then you’ll need
    to open up the standard HTTP/HTTPS ports (80 and 443) on your VM’s network
    firewall through the OpenStack Security Groups. To do this, create a new
    security group and add both the HTTP and HTTPS rules to it. Navigate to the
    virtual machine’s interfaces tab and add the new HTTP/HTTPS security group
    to it alongside the default security group.

11. While Gunicorn provides a server for uMap's Python code, using a generic web
    server as a reverse proxy and static file server can help uMap run a little
    more efficiently. While Apache and nginx are two popular options, we like to
    use Caddy because it automatically supports HTTPS and takes on the hassle of
    ensuring certificates are up to date.

    ```bash
    sudo apt install caddy
    sudo nano /etc/caddy/Caddyfile
    ```

    Modify the Caddyfile to serve static files and act as a reverse proxy to
    Gunicorn. Remember to replace `<domain_name>` with your registered domain
    name.

    ```{.sh filename="/etc/caddy/Caddyfile"}
    <domain_name> {
      encode zstd gzip
      request_body {
         max_size 5MB
      }

      handle /static/* {
         root * /srv/umap/var
         file_server
      }

      handle_path /uploads/* {
         root * /srv/umap/var/data
         file_server {
            hide datalayer
         }
      }

      reverse_proxy unix//srv/umap/umap.sock {
         header_down -Server
      }
    }
    ```

    Enable the caddy service to start the server.

    ```bash
    sudo systemctl enable --now caddy
    ```

12. As a final step, modify the umap.conf file to fit your needs. A few
    recommended modifications are listed below, but you can find more details in
    [uMap Documentation - Configuration](https://docs.umap-project.org/en/stable/config/settings/){target="\_blank"}.

    ```{.sh filename="/etc/umap/umap.conf"}
    ALLOWED_HOSTS = [
       "<domain_name>",
    ]

    DEBUG = False

    ADMINS = (("<name>", "<email>"),)

    Disable 3rd party authentication providers
    AUTHENTICATION_BACKENDS = (
    # "social_core.backends.github.GithubOAuth2",
    # "social_core.backends.bitbucket.BitbucketOAuth",
    # "social_core.backends.twitter.TwitterOAuth",
    # "social_core.backends.openstreetmap.OpenStreetMapOAuth",
    "django.contrib.auth.backends.ModelBackend",
    )

    # Remove the demo warning banner
    UMAP_DEMO_SITE = False

    # Disable anonymous users to avoid additional strain on your server
    UMAP_ALLOW_ANONYMOUS = False

    SITE_NAME = <your site name>

    SITE_DESCRIPTION = <a brief description of your site>

    SITE_URL = https://<domain name>

    # Set the default location to Vancouver, BC
    LEAFLET_LONGITUDE = -123
    LEAFLET_LATITUDE = 49.2
    LEAFLET_ZOOM = 9
    ```

    To see your changes implemented, restart the umap.socket.

    ```bash
    sudo systemctl restart umap.socket
    ```

## Tips and Tricks

uMap doesn't currently provide a method for uploading images or other media
files to be embedded in pop-ups. You'll need to serve those files from a
different location. We recommend requesting a public
[object storage](https://ubc-geography.github.io/computing-resources/cloud-computing/object-storage.html){target="\_blank"}
container/bucket and uploading your files there, so they can be easily embedded.

uMap also supports embedding
[iframes](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe){target="\_blank"}
in pop-ups, so if you have a more complex need for the content that you want to
be presented in a pop-up, you can create an HTML file with CSS and JavaScript
that fits your needs and then serve it from object storage.
