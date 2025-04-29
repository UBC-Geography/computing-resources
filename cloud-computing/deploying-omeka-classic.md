---
title: Deploying Omeka Classic
# change to date to last-modified after next modification
date: 2025-02-27
---

Omeka Classic is a free and open-source content management system that focuses
on supporting the development, curation, and sharing of digital exhibits.
Researchers with access to an Omeka Classic instance can upload digital media
files alongside a rich set of metadata that can help contextualize and highlight
relationships among different collection items.

This page provides a tutorial on how to deploy an Omeka Classic instance to an
Alliance Cloud virtual machine (VM) with the option to store media files in an
Arbutus Object Storage container (bucket). The deployment process is relatively
technical and has the following requirements:

- Status as faculty or a librarian with an institution that holds eligibility
  for CFI grants
- Working knowledge of UNIX/Linux
- A domain name

For alternative options that require less technical knowledge, both
[Omeka.net](https://www.omeka.net/) and
[Reclaim Hosting](https://www.reclaimhosting.com) provide affordable shared
hosting with Omeka either already installed or installable through an easy
one-click process.

Before setting up an Omeka Classic instance, it can be helpful to review the
Omeka Manual's
[Site Planning Tips](https://omeka.org/classic/docs/GettingStarted/Site_Planning_Tips/).
This will help you ensure your instance meets the needs of your project while
also identifying which features to pull into your instance through added
plugins.

## Installation

1. Canada-based faculty can access cloud computing resources through the
   Alliance Cloud. The best-suited resource for running an ongoing service is a
   [persistent virtual machine](https://ubc-geography.github.io/computing-resources/cloud-computing/#persistent-instances),
   which acts as a virtual private server.
   [Create an account](https://alliancecan.ca/en/services/advanced-research-computing/account-management/apply-account)
   with Alliance (if you haven't already done so) and submit a
   [Rapid Access Service request (RAS)](https://docs.google.com/forms/d/e/1FAIpQLSeU_BoRk5cEz3AvVLf3e9yZJq-OvcFCQ-mg7p4AWXmUkd5rTw/viewform)
   with the number of resources that you anticipate using. The following
   resource recommendations should accommodate the needs of most Omeka Classic
   instances, but you should request more if you anticipate heavy traffic or
   higher storage needs.

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
17.5 GB of storage for media assets. Omeka instances often require a significant
amount of storage, particularly when hosting large, high-quality video files.
Adjust your request for persistent storage as needed. If you plan on using more
than 50 GB of storage, consider including object storage in your request and
using that for as your media storage location. Details about integrating object
storage with an Omeka instance are noted
[below](https://ubc-geography.github.io/cloud-computing/deploying-omeka-classic.html#object-storage-optional).

:::

2. Once your request has been approved, the Alliance Cloud team will provide you
   with access to an OpenStack dashboard, where you'll be able to manage your
   allocated cloud resources. Follow the Alliance's
   [Cloud Quick Start](https://docs.alliancecan.ca/wiki/Cloud_Quick_Start) guide
   to set up an SSH key pair (if you haven't already generated one) and launch a
   persistent virtual machine. We recommend using the Debian image as your boot
   source. You should also review
   [security considerations with running a VM](https://docs.alliancecan.ca/wiki/Security_considerations_when_running_a_VM).

3. You should now have SSH access to your virtual machine, and you can start
   installing Omeka's system dependencies, which includes MariaDB, Apache2, PHP,
   and ImageMagick, with the following command. We'll also include Unzip, which
   will be used to extract the Omeka source code after downloading it from the
   developer's releases page.

   ```bash
   sudo apt install mariadb-server libapache2-mod-php php-mysql php-xml imagemagick unzip
   ```

4. Next we'll want to lock down MariaDB to improve its security by running the
   following command and running through the prompts that appear.

   ```bash
   sudo mysql_secure_installation
   ```

5. Now that the MariaDB installation has been secured, you can start setting up
   Omeka's database. Remember to replace `<password>` with a secure password.

   ```bash
   sudo mysql
   > CREATE USER 'omeka'@'localhost' IDENTIFIED BY '<password>';
   > CREATE DATABASE omeka CHARACTER SET utf8 COLLATE utf8_unicode_ci;
   > GRANT ALL PRIVILEGES ON omeka.* TO 'omeka'@'localhost';
   > exit;
   ```

6. With the system dependices installed and a secure database created, we can
   now download the Omeka source code from GitHub and extract it from the zip
   archive.

   ```bash
   wget https://github.com/omeka/Omeka/releases/download/v3.1.2/omeka-3.1.2.zip
   unzip omeka-3.1.2.zip
   ```

7. Ensure Omeka can access its database by modifying the db.ini config file to
   include the database name and user info. Again, replace `<password>` with the
   same password you provided in step 5.

   ```bash
   nano omeka-3.1.2/db.ini
   ```

   ```{.sh filename="~/omeka-3.1.2/db.ini"}
   ...
   [database]
   host        = "localhost"
   username    = "omeka"
   password    = "<password>"
   dbname      = "omeka"
   ...
   ```

8. Omeka relies on an Apache web server to render and serve pages, so we'll move
   Omeka's source code into Apache's default root directory and update the
   permissions on the source code files. This will enable Apache to read and
   execute Omeka's PHP code.

   ```bash
   sudo mv omeka-3.1.2 /var/www/omeka
   sudo chown -R www-data:www-data /var/www/omeka/files
   sudo chmod -R 755 /var/www/omeka/files
   ```

9. We'll then need to configure Apache, so it starts correctly serving files
   from the Omeka directory.

   ```bash
   sudo nano /etc/apache2/sites-available/000-default.conf
   ```

   ```{.sh filename="/etc/apache2/sites-available/000-default.conf"}
   ...
   DocumentRoot /var/www/omeka
   <Directory "/var/www/omeka" >
     AllowOverride All
   </Directory>
   ...
   ```

   ```bash
   sudo a2enmod rewrite
   sudo systemctl restart apache2
   ```

10. Through your domain name registrar, create a DNS A record that points your
    domain name or subdomain to your VM's floating IP address. Then you'll need
    to open up the standard HTTP/HTTPS ports (80 and 443) on your VM's network
    firewall through the OpenStack Security Groups. To do this, create a new
    security group and add both the HTTP and HTTPS rules to it. Navigate to the
    virtual machine's interfaces tab and add the new HTTP/HTTPS security group
    to it alongside the default security group.

11. Omeka should now be available through HTTP, but to ensure visitors can
    access it securely, a certificate will need to be acquired to enable HTTPS.
    Certbot is a great tool that can automate much of the process for you, and
    step-by-step instructions can be found
    [here](https://certbot.eff.org/instructions?ws=apache&os=pip).

12. Finally, access Omeka through your provided domain name and finalize the
    installation process by creating your user account. You now have a running
    Omeka instance can start uploading and describing your materials.

## Plugins (Optional)

Omeka provides the following plugins, which can be easily installed from the
Admin Plugins pages.

- COinS
- Exhibit Builder
- Simple Pages

Omeka also provides a comprehensive
[listing of additional plugins](https://omeka.org/classic/plugins/) along with
instructions on adding new plugins to your Omeka instance in the
[Omeka Classic Manual](https://omeka.org/classic/plugins/).

For many geographers, the Geolocation plugin will be a very helpful one to add,
so we've included instruction for installing it below:

1. Connect to your Omeka VM using SSH.

2. Download the Geolocation plugin source code.

   ```bash
   wget https://github.com/omeka/plugin-Geolocation/releases/download/v3.2.3/Geolocation-3.2.3.zip
   unzip Geolocation-3.2.3.zip
   ```

3. Move the Geolocation source code to Omeka's plugin directory

   ```bash
   sudo mv Geolocation /var/www/omeka/plugins
   ```

4. Open the Omeka Admin Plugins page in your web browser and install the
   Geolocation plugin. Once the installation is finished you should see a new
   map tab listed when uploading and describing new items.

## Object Storage (Optional)

Object storage, like AWS S3, is often cheaper and easier to request in larger
quantities than the traditional persistent storage assigned to a shared hosting
account or cloud VM. Reclaim Hosting provides a very helpful piece of
documentation on
[integrating AWS S3 with an Omeka Classic instance](https://support.reclaimhosting.com/hc/en-us/articles/1500005621161-Setting-up-S3-storage-with-Omeka-Classic)
running on their shared hosting services. This section adapts that documentation
with a focus on using the Alliance Cloud's Arbutus Object Storage and includes
the following requirements:

- A Unix or Unix-like shell
- Python and pip

As note earlier, you'll need to modify your RAS request to include an allocation
for object storage. Once that request has been approved, you'll be granted
access to the Arbutus OpenStack dashboard, where you'll be able to start
creating object storage containers, also known as buckets. We have brief
instruction on how to do so
[here](https://ubc-geography.github.io/computing-resources/cloud-computing/object-storage.html#digital-research-alliance-dra).
Note that you'll need ensure your object storage container is public to ensure
uploaded files are available to anonymous users.

To connect your Omeka instance to an Arbutus Object Storage container, you'll
need to generate an access key and a secret key using an OpenStack command line
tool. These credentials will then be used in your Omeka config file to
authenticate your instance to Arbutus Object Storage.

1. Before you can start using the OpenStack command line tool, you'll need to
   have access to a Unix or Unix-like shell, like BASH. MacOS and Linux users
   will already have this through their terminal applications while Windows
   users will need to install it, with the most recommended approach being Git
   BASH, which is included with [Git for Windows](https://gitforwindows.org/).

2. Next you'll download a shell script from the Arbutus OpenStack dashboard,
   called an OpenStack RC File, which can be found by opening the dropdown under
   your username in the upper right-hand corner of the OpenStack dashboard. And
   use the following command to run the OpenStack RC File, which will be used to
   authenticate the command line tool to manage your allocated resources.

   ```bash
   source <project-name>-openrc.sh
   ```

3. The OpenStack command line tool is distributed as a Python package, so you
   can install it using Python's package manager, `pip`. The following commands
   use `mamba` to install the tool into a virtual environment. You can learn
   more about `mamba` and virtual environments
   [here](https://ubc-geography.github.io/computing-resources/development-environments/conda-getting-started.html).

   ```bash
   mamba create -n openstack
   mamba activate openstack
   (openstack) python -m pip install python-openstackclient
   ```

4. With the OpenStack command line tool installed, you can now generate a new
   set of credentials that can then be used to authenticate your Omeka instance
   with your Arbutus project.

   ```bash
   (openstack) openstack ec2 credentials create
   ```

   When the credentials are generated, values will be provided for both an
   access key and a secret key. These are the equivalent of a username and
   password for your Alliance project, so record them and keep them secure.

5. Finally, you'll need to modify one of Omeka's config files to direct your
   instance to start using object storage by providing your access key, secret
   key, and the name of your container. Additionally, you'll need to update the
   adapter and endpoint using the values listed below.

   ```bash
   nano /var/www/omeka/application/config/config.ini
   ```

   ```{.sh filename="/var/www/omeka/application/config/config.ini"}
   ...
   ;
   storage.adapter = "Omeka_Storage_Adapter_ZendS3"
   storage.adapterOptions.accessKeyId = <access key>
   storage.adapterOptions.secretAccessKey = <secret key>
   storage.adapterOptions.bucket = <container name>
   ; storage.adapterOptions.expiration = 10 ; URL expiration time (in minutes)
   storage.adapterOptions.endpoint = https://object-arbutus.cloud.computecanada.ca
   storage.adapterOptions.forceSSL = 1 ; Boolean value (optional)

   ...
   ```

## Performance Tweaks (Optional)

In general, Making performance tweaks to your Omeka server can help both ensure
that its running as efficiently as possible while also improving access for
users that may network connections with limited bandwidth.

Enable apache2 expire mod and uncomment .htaccess
https://developer.chrome.com/docs/lighthouse/performance/uses-long-cache-ttl/?utm_source=lighthouse&utm_medium=devtools

Install brotli and enable brotli mod in apache

Connect a CDN (cloudfront via UBC IT Hybrid Cloud or fastly). works best with S3
storage ??? I don't know if this will work because Cloudfront and S3 url would
be different
