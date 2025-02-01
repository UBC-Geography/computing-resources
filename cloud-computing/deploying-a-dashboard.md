---
title: Deploying a Dashboard
---

This page provides a tutorial on how to deploy an interactive dashboard to an
Alliance Cloud virtual machine (VM) using a Jupyter notebook and the Jupyter
project, Voilà.

Adapted from the
[Voilà Deployment Guide](https://voila.readthedocs.io/en/stable/deploy.html#running-voila-on-a-private-server)
with some opinions.

Requirements:

- An interactive Jupyter notebook
- Status as faculty or a librarian with an institution that holds eligibility
  for CFI grants
- Working knowledge of UNIX/Linux
- Domain name

1. Canada-based faculty can access cloud computing resources through the
   Alliance Cloud. The best-suited resource for interactive dashboards is a
   [persistent virtual machine](https://ubc-geography.github.io/computing-resources/cloud-computing/#persistent-instances),
   which acts as a virtual private server.
   [Create an account](https://alliancecan.ca/en/services/advanced-research-computing/account-management/apply-account)
   with Alliance (if you haven't already done so) and submit a
   [Rapid Access Service request (RAS)](https://docs.google.com/forms/d/e/1FAIpQLSeU_BoRk5cEz3AvVLf3e9yZJq-OvcFCQ-mg7p4AWXmUkd5rTw/viewform)
   with the number of resources that you anticipate using. The following
   resource recommendations should accommodate a very simple dashboard, but you
   should request more if your dashboard will be running resource-intensive
   computations on large datasets.

   - vCPU: 1
   - Instances: 1
   - Volumes: 1
   - Volume snapshots: 0
   - RAM: 1.5
   - Floating IPs: 1
   - Persistent storage: 20
   - Object storage: 0
   - Shared filesystem storage: 0

2. Once your request has been approved, the Alliance Cloud team will provide you
   with access to an OpenStack dashboard, where you'll be able to manage your
   allocated cloud resources. Follow the Alliance's
   [Cloud Quick Start](https://docs.alliancecan.ca/wiki/Cloud_Quick_Start) guide
   to set up an SSH key pair (if you haven't already generated one) and launch a
   persistent virtual machine. We recommend using the Debian image as your boot
   source. You should also review
   [security considerations with running a VM](https://docs.alliancecan.ca/wiki/Security_considerations_when_running_a_VM).

3. You should now have SSH access to your virtual machine. If the Jupyter
   notebook that you are using for your dashboard is stored in a GitHub
   repository, you can clone it to your VM. Otherwise you can use `scp` to copy
   the notebook along with a requirements.txt or environment.yml file from your
   local machine to the VM.

   ```bash
   $ sudo apt install git
   $ git clone <your repo URL>
   ```

4. While Voila can be installed via Python and `pip`, we recommend installing it
   using `mamba` and running it from a `conda` environment. This will improve
   the reproducibility of your dashboard while also making it easier to maintain
   by providing more flexibility around Python and other software dependencies.

   ```bash
   $ curl -L -O "https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-$(uname)-$(uname -m).sh"
   $ bash Miniforge3-$(uname)-$(uname -m).sh
   $ mamba activate
   ```

5. If you've included an `environment.yml` or `requirements.txt` file alongside
   your notebook, use it to install any dependencies. Also install `voila` and
   `ipykernel` if needed.

   ```bash
   $ mamba env create -n <project_name> -f environment.yml
   $ mamba install -n <project_name> voila ipykernel
   ```

6. To ensure that `voila` starts running whenever your VM reboots, you'll need
   to create and enable a new `systemd` service. Use the following command to
   create the service config file.

   ```bash
   $ sudo nano /usr/lib/systemd/system/voila.service
   ```

   Then use the following text as a template for your service:

   ```txt
   [Unit]
   Description=Voila

   [Service]
   Type=simple
   PIDFile=/run/voila.pid
   ExecStart=mamba run -n <project_name> voila --no-browser voila/notebooks/<notebook_file>
   User=debian
   WorkingDirectory=/home/debian/
   Restart=always
   RestartSec=10

   [Install]
   WantedBy=multi-user.target
   ```

   Next enable and start the service with the following commands:

   ```bash
   $ sudo systemctl enable voila.service
   $ sudo systemctl start voila.service
   ```

7. By default, Voilà starts running from port 8866. Rather than opening this
   port from your virtual machine's network firewall through OpenStack Security
   Groups, we strongly recommend taking the additional step to setup a reverse
   proxy with a domain name, which will provide your dashboard with better
   performance and security.

   Apache, nginx, and Caddy are all popular options for reverse proxies. We'll
   use Caddy in this guide because it's the easiest one to setup.

   Through your domain name registrar, create a DNS A record that points your
   domain name or subdomain to your VM's floating IP address. Then you'll need
   to open up the standard HTTP/HTTPS ports (80 and 443) on your VM's network
   firewall through the OpenStack Security Groups. To do this, create a new
   security group and add both the HTTP and HTTPS rules to it. Navigate to the
   virtual machine's interfaces tab and add the new HTTP/HTTPS security group to
   it alongside the default security group.

   Finally, run the following commands in your virtual machine to install Caddy
   and start running it as a reverse proxy to Voilà.

   ```bash
   $ sudo apt install caddy
   $ sudo -E caddy reverse-proxy --from <your_domain_name> --to :8866
   ```

   Navigate to your dashboard to see it in action!
