# Using Containers for Development Environments

While Conda can provide extremely convenient development environments, you may
run into some instances where Conda does not afford you the level of isolation
required to install or run a piece of software that you need for your research.
This is an area where containers can be particularly useful as they provide a
valuable middle ground between a Conda virtual environment and a full virtual
machine.

For more information about containers and a few of the container engines
available, see
[Containers](https://github.com/UBC-Geography/computing-resources/tree/main/containers#containers).
To build and run containers on your local machine, you'll need to have one of
these engines installed.

## JupyterLab

The Jupyter team maintains a core set of container images that can be pulled and
used for your own development environment. These images can also be built upon
to create new container images that include and software you may need.

- [Jupyter Docker Stacks Documentation](https://jupyter-docker-stacks.readthedocs.io/en/latest/index.html)

Dockerfiles provide instructions for creating your customized container image.
These files can be easily shared and reused to build your container. The
following example walks through a basic Dockerfile that builds a new image based
on the jupyter/minimal-notebook image, which includes everything you need to get
Jupyter up and running with all the necessities. Review the
['Selecting an image'](https://jupyter-docker-stacks.readthedocs.io/en/latest/using/selecting.html)
when selecting a Jupyter image to build on top of.

Start by creating a new Dockerfile with your preferred text editor.

```bash
nano Dockerfile
```

Next, within the Dockerfile, write out the list of commands you would want to
run to create your development environment. Review the
[Dockerfile Reference](https://docs.docker.com/engine/reference/builder/) for
more details.

```Dockerfile
# Always start with a FROM instruction that points to an existing image
FROM docker.io/jupyter/minimal-notebook

# Switch to the root user to enable installing packages via APT
USER root

# Replace <apt_packages> with your APT dependencies
RUN apt-get update -y && \
    apt-get install -y --no-install-recommends \
    <apt_packages> && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

# Switch back to the default Jupyter user
USER {NB_UID}

# Replace <conda_forge_packages> with your Conda dependencies
RUN mamba install -y \
    <conda_forge_packages> &&
    mamba clean --all -f -y && \
    fix-permissions "${CONDA_DIR}" && \
    fix-permissions "/home/${NB_USER}"

# If any R dependencies aren't included on conda-forge, install them from CRAN.
RUN R -q -e 'install.packages(c(<CRAN_packages>),
                                repo="https://mirror.rcg.sfu.ca/mirror/CRAN/")'
```

Build your customized container image using the Dockerfile. Replace <image_name>
with a memorable name for your image.

```bash
docker build -t <image_name> .
```

Test your image!

```bash
docker run -it --rm -p 8888:8888 <image_name>
```

Follow the link provided by Jupyter in your terminal. You may need to substitute
`127.0.0.1` with `localhost` in the URL.

If you prefer using Podman over Docker to run containers, you can find some
additional details
[here](https://jupyter-docker-stacks.readthedocs.io/en/latest/using/running.html#using-the-podman-cli)
for running a Jupyter container in rootless mode.

## RStudio

The Rocker Project provides a very useful set of container images that are
R/RStudio-based equivalents to the Jupyter Docker Stack.

- [The Rocker Images](https://rocker-project.org/images/)

Both the `rocker/geospatial` and `rocker/ml-verse` (geospatial with CUDA
support) images are particularly worth noting as they include a wide array of
geospatial packages. You can find a list of geospatial packages installed in the
images
[here](https://github.com/rocker-org/rocker-versioned2/blob/master/scripts/install_geospatial.sh).

To build a new image on top of a Rocker image that includes an additional
selection of packages, create a new Dockerfile with your preferred text editor.

```bash
nano Dockerfile
```

Next write out the list of commands you would want to run to create your
development environment. Review the
[Dockerfile Reference](https://docs.docker.com/engine/reference/builder/) for
more details.

```Dockerfile
# Always start with a FROM instruction that points to an existing image
FROM docker.io/rocker/geospatial

# Replace <apt_packages> with any system packages that you need to install using APT
RUN apt-get update -y && \
    apt-get install -y --no-install-recommends \
    <apt_packages> && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

# Note: The Rocker images do not include Conda or Mamba, so you will need to check the system requirements for each of your R packages and ensure that any required system software is installed using APT.

# Rocker images come with a handy helper command, install2.r, to make installing R packages a bit simpler. The following command will only build the image if no errors are encountered, while also skipping any packages that may have already been installed and attempting to run the installation as quickly by using the maximum available CPU cores.
RUN install2.r --error --skipinstalled --ncpus -1 \
    <R_packages> \
    && rm -rf /tmp/downloaded_packages
```

Build your customized container image using the Dockerfile. Replace <image_name>
with a memorable name for your image.

```bash
docker build -t <image_name> .
```

Test your image!

```bash
docker run -it --rm -e PASSWORD=<your_password> -p 8787:8787 <image_name>
```

Navigate to
http://localhost:8787`in your browser and login to RStudio with username:`rstudio`
and <your_password>. With RStudio running in your browser, you should find a
large array of packages already installed and ready to be loaded.

If you prefer using Podman over Docker to run containers, follow the same
instructions as above, but sign into RStudio with `root` as the username.

## VS Code

Using a development container with VS Code can be easily managed using the
[Dev Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)
extension. You can also find more information on setting up and using
development containers
[here](https://code.visualstudio.com/docs/devcontainers/containers).

Prior to using development containers, again consider whether a
Conda/Mamba-based virtual environment would just as adequately meet your needs
as this can save you from adding further complexities to your project with
containers.

Within your project folder or local repository, create a directory named
`.devcontainer` and within the directory create a new file named
`devcontainer.json`. If a container image already exists that includes all the
packages you need for development, you can name the image you want to use within
the devcontainer.json file, like so:

```json
{
  "image": "docker.io/condaforge/mambaforge"
}
```

This would pull the `condaforge/mambaforge` container image that is hosted on
Docker Hub and create a new container from that image as my development
environment. From a terminal, you could then install packages with Mamba, but
any installed packages would not be preserved once the container is stops.

To ensure your development environment always starts with the specific set of
packages needed to run your code, you can create a Dockerfile, which would
specify exactly how to create your customized development environment.

You will need to start by editing the `devcontainer.json` to match the
following:

```json
{
  "build": {
    "dockerfile": "Dockerfile"
  }
}
```

Then you will need to create your `Dockerfile` within the `.devcontainer`
directory. Review the
[Dockerfile Reference](https://docs.docker.com/engine/reference/builder/) for
more details on creating a Dockerfile.

The following example would start with an Ubuntu base image and install packages
using APT, Mamba/Conda, and/or R's CRAN.

```Dockerfile
FROM docker.io/docker/ubuntu

# Replace <apt_packages> with your APT dependencies
RUN apt-get update -y && \
    apt-get install -y --no-install-recommends \
    <apt_packages> && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

# Replace <conda_forge_packages> with your Conda dependencies
RUN mamba install -y \
    <conda_forge_packages> && \
    mamba clean --all -f -y

# If any R dependencies aren't included on conda-forge, install them from CRAN.
RUN R -q -e 'install.packages(c(<CRAN_packages>),
                              repo="https://mirror.rcg.sfu.ca/mirror/CRAN/")'
```

Hold down `ctrl`+`shift`+`p` to open VS Code's command pallette and run the
command 'Dev Containers: Reopen in Container' if you are creating the container
for the first time or 'Dev Containers: Rebuild and Reopen Container' if not. You
can then start editing and running your code within the development container.
