# Containers

Similar to virtual machines, containers are a form of virtualization that
package software and the multiple dependencies required to run that software
into a single, distributable environment. That container can then be run on any
system that is running the appropriate engine (Docker, Podman, etc.). They are
often lighter and more agile than virtual machines but can include increased
security risks if not deployed correctly. In general, virtual environments
managed using tools like Conda as discussed in
['Getting started with Conda, Virtual Environments, and Python'](/development-environments/conda-getting-started.md)
should provide sufficient isolation for most geospatial computing cases without
the need to familiarize oneself with container technologies, but containers can
be a helpful tool in cases when neither virtual environments or virtual machines
are feasible.

For examples on leveraging containers to run highly-customized development
environments with Jupyter, RStudio, or VS Code, see
[Using Containers for Development Environments](/development-environments/containerized-environments.md).

It is important to note that most containers can only run in Linux environments.
Each of the container systems listed below include tools and steps for setting
up simple, Linux environments from which containers can be ran on either Windows
or Mac machines.

Additionally, a large majority of container images are built with a simplified
Linux distribution (often Ubuntu) as their base image. While some images have
been built with Windows Server as their base image, it is important to note that
these images cannot and likely never will run a desktop environment and/or
graphical user interface (GUI).

## Container Images

There are many open container registries, where you can find publicly shared
container images. [Docker Hub](https://hub.docker.com) is one of the most
popular options and can be a useful tool when searching for images. In general,
you should be careful when selecting images and be sure to select images that
are well-maintained. If you need a very minimal environment with Conda/Mamba,
Conda-forge's [mambaforge](https://hub.docker.com/r/condaforge/mambaforge) image
can be a good place to start as you'll be able to install packages with
[APT](https://manpages.debian.org/bookworm/apt/apt-get.8.en.html) or
[Mamba](https://mamba.readthedocs.io/en/latest/index.html).

### Python

- [Jupyter - Minimal Notebook](https://jupyter-docker-stacks.readthedocs.io/en/latest/using/selecting.html#jupyter-minimal-notebook):
  A Jupyter server running JupyterLab and a Python kernel. No geospatial
  packages are included in this environment, but it is an excellent base image
  for creating customized Jupyter environments.

- [GDS_ENV - GDS_PY](https://darribas.org/gds_env/stacks/gds_py/): Built on top
  of Jupyter - Minimal Notebook, this image includes a large selection of Python
  geospatial packages.

### R

- [Jupyter - R Notebook](https://jupyter-docker-stacks.readthedocs.io/en/latest/using/selecting.html#jupyter-r-notebook):
  Similarly built from Jupyter - Minimal Notebook, this image includes an R
  kernel and a few R packages. Custom R environments with a preference towards
  JupyterLab should use this as their base image.

- [GDS_ENV - GDS](https://darribas.org/gds_env/stacks/gds/): Built on top of
  GDS_ENV - GDS_PY, this image includes an R kernel and a wide selection of R
  geospatial packages.

- [Rocker - Geospatial](https://rocker-project.org/images/versioned/rstudio.html):
  Swapping JupyterLab for RStudio, this container image includes a range of R
  packages with a heavy focus on geospatial research.

### Others

- [PostGIS](https://github.com/postgis/docker-postgis)

- [GeoServer](https://docs.geoserver.org/latest/en/user/installation/docker.html)

- [QGIS Server](https://docs.qgis.org/latest/en/docs/server_manual/containerized_deployment.html)

## Engines

### Apptainer (formerly Singularity)

Developed specifically for academic and high performance computing, Apptainer
avoids some of the security pitfalls of other engines, like Docker, at the
expense of certain functionalities. Apptainer can only run a specific container
format, but it provides all the necessary tools to complete conversions.

- [Apptainer Documentation](https://apptainer.org/docs/user/main/)

- [Running Apptainer on an Alliance cluster](https://docs.alliancecan.ca/wiki/Apptainer)

- [Running Apptainer on UBC ARCSockeye](https://confluence.it.ubc.ca/display/UARC/Using+Apptainer+or+Singularity+Containers)

For a few simple examples on using and running Apptainer, see
[High Performance Computing (HPC)](/high-performance-computing/README.md).

### Podman

Similar to Apptainer, Podman avoids some of the security pitfalls found in
Docker, but unlike Apptainer, Podman provides a more general-purpose container
engine. When developing containers, Podman can provide a more flexible and
feature-rich set of tooling compared to Apptainer. A common workflow may include
building containers with Podman and then converting them to Apptainer containers
prior to running in an HPC environment.

- [Podman Documentation](https://docs.podman.io/en/latest/)

- _[Podman in Action](https://go.exlibris.link/XZMWFsdp)_

### Docker

Docker is by far the most popular container system, so similar to Podman, it can
provide a helpful tool for developing and running containers on your local
machine. If you are still new to managing and running containers, Docker can be
a good system to get started with because of the large collection of resources
and tools that have been built around it.

- [UBC Library Research Commons - Introduction to Docker](https://ubc-library-rc.github.io/intro-docker)

- [Docker Documentation](https://docs.docker.com/get-started/)

- _[Docker: Up and Running](https://go.exlibris.link/z6bLGnqS)_

- _[Practical Docker with Python](https://go.exlibris.link/V5Yl7J3v)_

- _[Docker Deep Dive](https://go.exlibris.link/4wT3cjWD)_
