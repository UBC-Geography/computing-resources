# Containers

Similar to virtual machines, containers are a form of virtualization
that packages software and the multiple dependencies required to run
that software into a single container. That container can then be run on
any system that is running the appropriate engine. They are often
lighter and more agile than virtual machines but can include increased
security risks.

## Apptainer (formerly Singularity)

Developed specifically for academic and high-performance computing.
Apptainer avoids some of the security pitfalls of other engines like
Docker at the expense of certain functionalities. Apptainer can only run
a specific container format, but it provides all the necessary tools to
complete conversions.

- [Apptainer Documentation](https://apptainer.org/docs/user/main/)

- [Running Apptainer on an Alliance cluster](https://docs.alliancecan.ca/wiki/Apptainer)

- [Running Apptainer on UBC ARCSockeye](https://confluence.it.ubc.ca/display/UARC/Using+Apptainer+or+Singularity+Containers)

## Podman

- [Podman Documentation](https://docs.podman.io/en/latest/)

## Docker

- [UBC Library Research Commons - Introduction to Docker](https://ubc-library-rc.github.io/intro-docker)

- [Docker Documentation](https://docs.docker.com/get-started/)
