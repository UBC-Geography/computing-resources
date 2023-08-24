# Containers

Similar to virtual machines, containers are a form of virtualization that
packages software and the multiple dependencies required to run that software
into a single, distributable container. That container can then be run on any
system that is running the appropriate engine. They are often lighter and more
agile than virtual machines but can include increased security risks.

It's important to note that most containers can only run in Linux environments.
Each of the container systems listed below include tools and steps for setting
up simple, Linux environments from which containers can be ran on either Windows
or Mac machines.

## Apptainer (formerly Singularity)

Developed specifically for academic and high-performance computing, Apptainer
avoids some of the security pitfalls of other engines like Docker at the expense
of certain functionalities. Apptainer can only run a specific container format,
but it provides all the necessary tools to complete conversions.

- [Apptainer Documentation](https://apptainer.org/docs/user/main/)

- [Running Apptainer on an Alliance cluster](https://docs.alliancecan.ca/wiki/Apptainer)

- [Running Apptainer on UBC ARCSockeye](https://confluence.it.ubc.ca/display/UARC/Using+Apptainer+or+Singularity+Containers)

## Podman

Similar to Apptainer, Podman avoids some of the security pitfalls found in
Docker, but unlike Apptainer, Podman provides a more general-purpose container
engine. When developing containers, Podman can provide a more flexible and
feature-rich set of tooling compared to Apptainer. A common workflow may include
building containers with Podman and then converting them to Apptainer containers
prior to running in an HPC environment.

- [Podman Documentation](https://docs.podman.io/en/latest/)

- _[Podman in Action](https://go.exlibris.link/XZMWFsdp)_

## Docker

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
