---
output-file: index.html
title: High-Performance Computing / High-Throughput Computing
date: last-modified
---

High-performance computing (HPC) and high-throughput computing (HTC) can provide
a powerful solution when working with incredibly large datasets as they allow
you and your collaborators to run scripts and programs over those datasets
without facing limitations in your hardware and network speeds. UBC's Advanced
Research Computing provides access to HPC/HTC resources via their Sockeye
compute cluster along with secure and redundant digital object storage via
Chinook. Additionally, the Canada-based organization, Digital Research Alliance,
provides compute clusters across Canada, including one located at Simon Fraser
University.

- [Introduction to Compute Canada (Alliance) Video](https://www.youtube.com/watch?v=hWkWAaNBILs){target="\_blank"}

- [Intro to Linux and the Bash Shell in HPC Environments](https://confluence.it.ubc.ca/display/UARC/Introduction+to+Linux+and+Using+the+Command+Line+Interface){target="\_blank"}

- [HPC Carpentry - Community Developed Lessons](https://www.hpc-carpentry.org/community-lessons/){target="\_blank"}

- [Research Computing Bootcamp Videos](https://www.ualberta.ca/information-services-and-technology/research-computing/bootcamps.html?1=HPC){target="\_blank"}

- [Geospatial Analysis with HPC Video](https://youtu.be/wRmRnVMjKXM){target="\_blank"}

- _High Performance Computing for Geospatial Applications_ :
  [UBC Library](https://go.exlibris.link/619Mq3H3){target="\_blank"} |
  [WorldCat](https://search.worldcat.org/title/1178714505){target="\_blank"}

- [Supercomputing Conference - Recorded Sessions](https://www.youtube.com/@SCconferenceseries/playlists){target="\_blank"}

- _Parallel and High Performance Computing_ :
  [UBC Library](https://go.exlibris.link/1VWhVDjZ){target="\_blank"} |
  [WorldCat](https://search.worldcat.org/title/1262371463){target="\_blank"}

## UBC Advanced Research Computing Sockeye

Documentation:
<https://confluence.it.ubc.ca/display/UARC/Using+Sockeye>{target="\_blank"}

Resource Limits:

- HTC:
  - 40 cores (Gold 6230), 754 GB of RAM
- HPC (non-blocking):
  - CPU-Intensive:
    - 1,000 cores on 25 nodes, 186 GB of RAM per node
  - Memory-Intensive:
    - 320 cores on 8 nodes, 754 GB of RAM per node
    - 640 cores on 16 nodes, 376 GB of RAM per node

Supported Software:
<https://confluence.it.ubc.ca/display/UARC/Software>{target="\_blank"}

::: {.callout-note}

Linux (Rocky Linux) software can be installed along with conda packages or any
software available within an Apptainer container.

:::

## Digital Research Alliance Clusters

Resources held on the Alliance HPC clusters are available for any Canada-based
faculty or academic librarian to use. To start submitting jobs to one of the
clusters listed below, register for an account with the Alliance using this
[link](https://ccdb.alliancecan.ca/account_application){target="\_blank"}.
Graduate students and university staff can also register an account and submit
jobs through an active sponsorship from a registered faculty member or principal
investigator.

The HPC clusters uses a job scheduler to manage and share resources as
efficiently as possible. This means that jobs are not completed on a first-come,
first-served basis, rather multiple factors can impact when a job is finally
run, which can make it difficult to estimate how long a job will wait in the
queue. In general running shorter jobs on fewer resources can significantly
reduce wait times, so ensure that you are optimizing your code as much as
possible. If you plan on using a cluster extensively (200 core-years or more)
and/or need higher prioritization from the scheduler, you should review and
submit an application (due at the end of October) to the Alliance's annual
[Resource Allocation Competition (RAC)](https://alliancecan.ca/en/services/advanced-research-computing/accessing-resources/resource-allocation-competition/resource-allocation-competition-application-guide){target="\_blank"}.
This additionally enables you to request access to the Niagara cluster and
receive larger allocations of storage.

Documentation:
<https://docs.alliancecan.ca/wiki/Getting_started>{target="\_blank"}

::: {.callout-note}

The Alliance is currently in the process of implementing significant upgrades to
their HPC systems, so the information listed below may no longer be up to date.
For details on the status of current upgrades, review the
[Infrastructure Renewal](https://docs.alliancecan.ca/wiki/Infrastructure_renewal)
page on their wiki.

:::

Clusters:

- [Cedar (SFU)](https://docs.alliancecan.ca/wiki/Cedar){target="\_blank"}
  - Resource Limits:
    - HTC:
      - CPU-Intensive:
        - 48 cores (Platinum 8160F), 187 GB of RAM
      - Memory-Intensive:
        - 40 cores (Gold 5215), 6,000 GB of RAM
    - HPC (non-blocking):
      - CPU-Intensive:
        - 1,536 cores on 32 nodes, 187 GB of RAM per node
      - Memory-Intensive:
        - 96 cores on 3 nodes, 4,000 GB of RAM per node
        - 256 cores on 8 nodes, 1,510 GB of RAM per node
        - 640 cores on 20 nodes, 502 GB of RAM per node
- [Graham (UW)](https://docs.alliancecan.ca/wiki/Graham){target="\_blank"}
  - Resource Limits:
    - HTC:
      - 64 cores (E7-4850 v4), 3,022 GB of RAM
    - HPC (non-blocking):
      - CPU-Intensive:
        - 1,024 cores on 32 nodes, 125 GB of RAM per node
      - Memory-Intensive:
        - 192 cores on 3 nodes, 3,022 GB of RAM per node
        - 768 cores on 24 nodes, 502 GB of RAM per node
- [Niagara (U of T)](https://docs.alliancecan.ca/wiki/Niagara){target="\_blank"}
  (RAC-only)
  - Resource Limits:
    - HTC:
      - 40 cores (Skylake CPU), 202 GB of RAM
    - HPC (non-blocking):
      - 17,280 cores on 432 nodes, 202 GB of RAM per node
- [Béluga (McGill)](https://docs.alliancecan.ca/wiki/B%C3%A9luga){target="\_blank"}
  - Resource Limits:
    - HTC:
      - 40 cores (Gold 6148), 752 GB of RAM
    - HPC (non-blocking):
      - 640 cores on 16 nodes, 752 GB of RAM per node
- [Narval (UQ)](https://docs.alliancecan.ca/wiki/Narval){target="\_blank"}
  - Resource Limits:
    - HTC:
      - 64 cores (Epyc 7502), 4,000 GB of RAM
    - HPC (non-blocking):
      - 3,584 cores on 56 nodes, 249 GB of RAM per node

Supported Software:
<https://docs.alliancecan.ca/wiki/Available_software>{target="\_blank"}

::: {.callout-note}

Additionally, any software that can be installed within an Apptainer container.

:::

## QGIS

QGIS can run on either UBC Sockeye or Alliance clusters. To interact with QGIS
through a graphical user interface, you'll need to run it within an interactive
job with X11 forwarding enabled. You can find more information on creating
graphical interactive jobs on UBC Sockeye
[here](https://confluence.it.ubc.ca/display/UARC/Running+Jobs#RunningJobs-GraphicalInteractive){target="\_blank"},
while QGIS-specific documentation for Alliance clusters is listed below.

- [Alliance Documentation - QGIS](https://docs.alliancecan.ca/wiki/QGIS){target="\_blank"}

Alternatively, you can run QGIS from an Alliance cluster and access it directly
through your browser by using one of the JupyterHub instances noted in the next
section. Generally, we recommend requesting a Jupyter server on the Graham
cluster because it provides access to more resources and is largely focused on
supporting visualization workflows. You should also request at least 2 CPU cores
and 4 GB of RAM to effectively run QGIS.

Once your Jupyter server has been allocated and started, launch the Desktop
application from the JupyterLab launcher. This will open a Linux-based desktop
environment, which is running on your Jupyter server resources, in separate
browser tab. Next open a terminal in the desktop environment and enter the
following commands to load and then start QGIS.

```bash
$ module load gcc
$ module load qgis
$ qgis
```

## Jupyter

A handful of Alliance clusters provide access to hardware via a JupyterHub
instance. While hardware resources are significantly restricted, using Jupyter
can provide an easy method for familiarizing oneself with the software and
capabilities of an HPC environment. JupyterHub provides an easy-to-follow form
for setting up an interactive job on a given cluster, where your Jupyter server
will be running from.

- [Alliance Documentation - JupyterHub](https://docs.alliancecan.ca/wiki/JupyterHub){target="\_blank"}

- [Working with Jupyter on Clusters (Alliance) Video](https://youtu.be/Qk3Le5HBxeg?si=IANIgAciBdOLwMQy){target="\_blank"}

- Clusters Running JupyterHub (requires an Alliance account):

  - [Cedar (SFU)](https://jupyterhub.cedar.computecanada.ca/){target="\_blank"}

    - Resource Limits:
      - Time (Session Length): 30 minutes - 5 hours
      - CPU Cores: 8
      - Memory: 46 GB
      - GPUs: 4 x V100L

  - [Graham (UW)](https://jupyterhub.graham.computecanada.ca/){target="\_blank"}

    - Resource Limits:
      - Time (Session Length): 15 minutes - 24 hours
      - CPU-Intensive:
        - Cores: 128
        - Memory: 2,000 GB
        - GPUs: 8 x A100
      - Memory-Intensive:
        - Cores: 64
        - Memory: 3,022 GB
        - GPUs: none

  - [Béluga (McGill)](https://jupyterhub.beluga.computecanada.ca/){target="\_blank"}

    - Resource Limits:
      - Time (Session Length): 1 - 12 hours
      - CPU Cores: 10
      - Memory: 46 GB
      - GPUs: 1 x V100

  - [Narval (UQ)](https://jupyterhub.narval.computecanada.ca/){target="\_blank"}
    - Resource Limits:
      - Time (Session Length): 1 - 8 hours
      - CPU Cores: 16
      - Memory: 78 GB
      - GPUs: 1 x A100

- Supported Kernels (Programming Languages):

  - Python 2.7, 3.6, 3.7, 3.8, 3.9 (default), 3.10, and 3.11

  - R 4.2

  - Julia 1.5 & 1.8

::: {.callout-note}

Other kernels can be supported using Apptainer containers.

:::

::: {.callout-note}

You can only install packages from Alliance's maintained set of
[Python wheels](https://docs.alliancecan.ca/wiki/Available_Python_wheels){target="\_blank"}.
To run JupyterLab with conda or external libraries held on PYPI or CRAN, you'll
need to run it using a pre-built Apptainer container as documented in the
alternative approaches below.

:::

- Alternatives Approaches for Running JupyterLab:

  - [Alliance - Instructions for running JupyterLab via a virtual environment](https://docs.alliancecan.ca/wiki/Advanced_Jupyter_configuration){target="\_blank"}

  - [UBC ARC Sockeye - Instructions for running JupyterLab via an Apptainer container](https://confluence.it.ubc.ca/display/UARC/Jupyter+Notebooks+with+Singularity){target="\_blank"}

### Running a Jupyter Kernel from a Container

Containers enable you to pre-build customized environments from which you can
run software that is not supported on the Alliance clusters, and they can be
leveraged to extend the Alliance's JupyterHub clusters by running them as a
custom Jupyter kernels. This can be extraordinarily useful considering Conda is
not supported on the cluster.

Before using this approach, double-check that the software you need is not
already available on the cluster either as
[modules](https://docs.alliancecan.ca/wiki/Available_software){target="\_blank"}
or
[Python wheels](https://docs.alliancecan.ca/wiki/Available_Python_wheels){target="\_blank"}.
Software installed within a container is going to perform less efficiently than
equivalent modules on Alliance, which have been optimized for HPC.

#### Creating the container environment with Micromamba (Conda)

While this can be done within the Alliance login node, it is highly recommended
that the containers are built from another Linux environment and copied onto the
cluster. This will ensure that the build runs a bit faster and you aren't
competing for resources with other researchers on the login node.

Apptainer will only run on Linux, so Windows and MacOS users will need to
install a Linux virtual machine either via Windows Subsystem for Linux (WSL) or
Lima to create and run Apptainer containers locally. Apptainer includes
instructions in their documentation at this
[link](https://apptainer.org/docs/admin/main/installation.html#installation-on-windows-or-mac){target="\_blank"}.

::: {.callout-note}

Whenever you start a new Jupyter server on the cluster, you'll need to load the
apptainer module again in order for the kernel to run.

:::

1. Ensure Apptainer is installed in the Linux environment

   ```bash
   $ apptainer --version
   ```

If Apptainer is not installed, you can use the following steps on Debian or
Ubuntu

```bash
$ sudo apt update
$ sudo apt install -y software-properties-common
$ sudo add-apt-repository -y ppa:apptainer/ppa
$ sudo apt update
$ sudo apt install -y apptainer
```

2. Pull the mambaorg/micromamba Docker container from Docker Hub and build a
   sandbox container from it. This will enable you to use Micromamba, an
   alternative to Conda and Mamba that runs more efficiently in environments
   where resources are limited.

   ```bash
   $ apptainer build --sandbox <container_name>/ docker://mambaorg/micromamba:bookworm-slim
   ```

3. Start a Bash shell within the sandbox container with write privileges.

   ```bash
   $ apptainer shell -C --shell /bin/bash --writable <container_name>
   ```

4. Update Micromamba.

   ```bash
   Apptainer> micromamba self-update
   ```

5. Use Micromamba to install the kernel package needed for your preferred
   programming language (Python: ipykernel; R: r-irkernel) and any other
   packages you may need.

   ```bash
   Apptainer> micromamba install -y -q -n base -c conda-forge <kernel_package> <other_packages>
   ```

6. Clean up any extra files that are no longer needed

   ```bash
   Apptainer> micromamba clean --all -y
   ```

7. Exit the sandbox container shell

   ```bash
   Apptainer> exit
   ```

8. Build your Apptainer container from the sandbox container. Including a time
   stamp with `<container_name>` is recommended when building a container as you
   may want to rebuild the container with updated packages in the future.

   ```bash
   $ apptainer build <container_name>_<timestamp>.sif <container_name>
   ```

If you need flexibility in your container to add and remove packages, you can
create a sandbox environment from your uploaded container and modify the sandbox
container while accessing the cluster on a login node.

#### Installing a Micromamba Python-Based Container as a Kernel

1. Start a server on the JupyterHub cluster.

2. Start a new terminal.

3. Load the apptainer module.

   ```bash
   $ module load apptainer
   ```

4. Close the terminal and start a new one.

5. Install the container as a Python kernel

   ```bash
   $ python -m ipykernel install --user --name <container_name> --display-name="Python (<container_name>)"
   ```

6. The previous step provided an initial configuration for the kernel, but we
   will need to slightly modify it to ensure the kernel executes from the
   container.

   ```bash
   $ nano /home/<username>/.local/share/jupyter/kernels/<container_name>/kernel.json
   ```

   Modify kernel.json file to match the following:

   ```json {.json filename='kernel.json'}
   {
     "argv": [
       "apptainer",
       "exec",
       "/home/<username>/<container_name>.sif",
       "micromamba",
       "run",
       "python",
       "-m",
       "ipykernel_launcher",
       "-f",
       "{connection_file}"
     ],
     "display_name": "Python (<container_name>)",
     "language": "python",
     "metadata": {
       "debugger": true
     }
   }
   ```

7. Close the terminal and wait a few seconds for the kernel to register in the
   JupyterLab launcher.

#### Installing an R-Based Container as a Kernel

1. Start a server on the JupyterHub cluster.

2. Start a new terminal.

3. Load the apptainer module.

   ```bash
   $ module load apptainer
   ```

4. Close the terminal and start a new one.

5. Using the `nano` text editor, create a new directory and file to store the
   custom Jupyter kernel configuration

   ```bash
   $ nano <container_name>/kernel.json
   ```

   Within the kernel.json file, enter the following:

   ```json {.json filename='kernel.json'}
   {
     "argv": [
       "apptainer",
       "exec",
       "/home/<username>/<container_name>.sif",
       "micromamba",
       "run",
       "R",
       "--slave",
       "-e",
       "IRkernel::main()",
       "--args",
       "{connection_file}"
     ],
     "display_name": "R (<container_name>)",
     "language": "R",
     "metadata": {
       "debugger": true
     }
   }
   ```

6. Install the container as a custom kernel using the kernel.json file.

   ```bash
   $ jupyter kernelspec install <container_name> --user
   ```

7. Close the terminal and wait a few seconds for the kernel to register in the
   JupyterLab launcher.

## RStudio Server

### via JupyterHub

The easiest way to start an RStudio session in a HPC environment is to launch it
within a JupyterLab session. See the entry above for session limits and
documentation on starting a JupyterLab session from a JupyterHub cluster. Once
your JupyterLab session is running, select the Software tab in the sidebar and
find/load the rstudio-server module. You can then click the RStudio launcher, to
open a new RStudio session. While you can install any R library from CRAN, you
can't use package managers like conda and can only use software loaded as
modules from the Alliance. If you need more flexibility for your RStudio
session, setup and run your environment within an Apptainer container as
documented below.

### [via Container](https://confluence.it.ubc.ca/display/UARC/RStudio+with+Apptainer){target="\_blank"}

::: {.callout-note}

the linked instructions above cover running RStudio Server on the UBC ARC
Sockeye cluster using Apptainer, but the instructions should be extremely
similar for running on an Alliance cluster.

:::

- Instructions for creating an Apptainer container with pre-installed
  dependencies:

  - You can either build your container on a local Linux system and copy the
    container to the cluster or build it directly on a login node.

  - Example of building an RStudio container on a local Linux (Ubuntu) system

    ```bash
    # Install Apptainer if not already done so
    $ sudo apt update
    $ sudo apt install -y software-properties-common
    $ sudo add-apt-repository -y ppa:apptainer/ppa
    $ sudo apt update
    $ sudo apt install -y apptainer
    # Build a new sandbox container from one of the Rocker Project images
    # The geospatial images includes a range of geospatial packages
    $ apptainer build --sandbox rstudio/ docker://rocker/geospatial
    # Run a shell within the sandbox container with write and sudo privileges
    $ apptainer shell --writable --fakeroot rstudio/
    # Start R and install any additional packages that may be needed
    Apptainer> R
    R version 4.4.1 (2024-06-14) -- "Race for Your Life"
    ...
    > install.packages('climatol')
    ...
    > q()
    Apptainer> exit
    # Convert the sandbox container into a SIF container to be transferred to the HPC cluster
    $ apptainer build rstudio.sif rstudio
    ```

## Python

Prior to running Python in an HTC/HPC environment, ensure you have optimized
your code as much as possible. You can find resources relevant to parallelizing
Python code via system and external libraries, like multiprocessing, Dask, and
mpi4py, under
[Python - Increasing Performance](https://ubc-geography.github.io/computing-resources/python/#increasing-performance){target="\_blank"}.

- [Alliance Documentation - Python](https://docs.alliancecan.ca/wiki/Python){target="\_blank"}

- Supported Versions: 2.7, 3.6, 3.7, 3.8, 3.9, 3.10, 3.11 and 3.12

- Supported Virtual Environment Managers:

  - UBC ARC Sockeye:

    - conda, virtualenv, and venv

    - [Using Virtual Environments on Sockeye](https://confluence.it.ubc.ca/display/UARC/Using+Virtual+Environments+on+Sockeye){target="\_blank"}

  - Alliance: virtualenv or venv. conda is not supported, but it can be run
    using an Apptainer container. In general, Alliance recommends avoiding
    conda-forge and Anaconda packages if possible. Go
    [here](https://docs.alliancecan.ca/wiki/Anaconda/en){target="\_blank"} for
    more details. See instructions below for creating and running micromamba, a
    lightweight, drop-in replacement for conda, from an Apptainer container:

    - Creating an Apptainer container with conda and Anaconda packages:

      ```bash
      # Pull the micromamba Docker container and create a new sandbox container from it
      $ apptainer build --sandbox container/ docker://mambaorg/micromamba:bookworm-slim
      # Run a shell with write access in the sandbox container
      $ apptainer shell --writable -C --shell /bin/bash
      # Update micromamba
      Apptainer> micromamba self-update
      # Install some packages from conda-forge
      Apptainer> micromamba install -n base python=3.11 <package_names>
      Apptainer> exit
      # Convert the sandbox container into a SIF container
      $ apptainer build <container_name>_<timestamp>.sif container/
      ```

    - SLURM job script for running a Python script within the container created
      above:

      ```bash
      #!/bin/bash
      # Include the shebang at the top of the file, to clearly identify that the following script is meant for the Bash Shell
      # Provide flags as comments in the script. These will be read by SLURM to set option flags
      # Identify your user account
      #SBATCH --account=def-someuser
      # Identify the amount of memory to use per CPU
      #SBATCH --mem-per-cpu=1.5G  # In this case the job will only use one CPU with 1.5 GB of memory
      #SBATCH --time=1:00:00 # And I expect that the job will take a little less than an hour
      # At the beginning of your job load the Apptainer module
      $ module load apptainer
      # Run a Python script using an environment within your conda container
      $ apptainer run -C -B <directory holding Python script> -W $SLURM_TMPDIR <container_name>_<timestamp>.sif micromamba run python <script>
      ```

- Supported Packages (Alliance):
  <https://docs.alliancecan.ca/wiki/Available_Python_wheels>{target="\_blank"}

  - Note: include `--no-index` flag with `pip` to only install Alliance wheels.
    The Alliance Python wheels have been specifically compiled and optimized to
    run as effectively on HPC clusters as possible.

- Example Job Script:

  ```bash
  #!/bin/bash
  # Include the shebang at the top of the file, to clearly identify that the following script is meant for the Bash Shell
  # Provide flags as comments in the script. These will be read by SLURM to set option flags
  # Identify your user account
  #SBATCH --account=def-someuser
  # Identify the amount of memory to use per CPU
  #SBATCH --mem-per-cpu=1.5G  # In this case the job will only use one CPU with 1.5 GB of memory
  #SBATCH --time=1:00:00 # And I expect that the job will take a little less than an hour
  # At the beginning of your job load any software dependencies needed for your job
  module load python/3.10
  # If running Python, create and activate a virual environment
  virtualenv --no-download $SLURM_TMPDIR/venv
  source $SLURM_TMPDIR/venv/bin/activate
  # Upgrade pip and install Python dependencies using Alliance wheels listed as dependencies in requirements.txt
  python -m pip install --no-index --upgrade pip
  python -m pip install --no-index -r requirements.txt
  # Run the script
  python -m script.py
  # Deactivate the virtual environment
  deactivate
  ```

- Interactive Sessions:

  - [Sockeye](https://confluence.it.ubc.ca/display/UARC/Running+Jobs#RunningJobs-Interactive){target="\_blank"}

  - Alliance

    - Use the Slurm allocation
      ([salloc](https://docs.alliancecan.ca/wiki/Running_jobs){target="\_blank"})
      command

    - Example command for starting a single core IPython session on Alliance:

      ```bash
      $ salloc --time=00:15:00
      salloc: Pending job allocation 1234567
      ...
      salloc: Nodes cdr<###> are ready for your job
      $ module load gcc/9.3.0 python/3.10
      $ virtualenv --no-download venv
      $ source venv/bin/activate
      (venv) $ python -m pip install --no-index ipython
      (venv) $ ipython
      Python 3.10.2 ...
      ...
      In [1]: <python code>
      ...
      In [2]: exit
      (venv) $ deactivate
      $ exit
      salloc: Relinquishing job allocation 1234567
      ```

### Other Resources

- [Working with the Python Dask (Parallelization) Library Video](https://youtu.be/uGy5gT2vLdI){target="\_blank"}

## R

Prior to running R in an HTC/HPC environment, ensure you have optimized your
code as much as possible. You can find resources relevant to parallelizing R
code via system and external libraries, like parallel, data.table and snowfall,
under
[R - Increasing Performance](https://ubc-geography.github.io/computing-resources/r/#increasing-performance){target="\_blank"}.

- [Alliance Documentation - R](https://docs.alliancecan.ca/wiki/R){target="\_blank"}

- Supported Versions: 4.0, 4.1, 4.2, 4.3, and 4.4

- Example Job:

  ```bash
  #!/bin/bash
  #SBATCH --account=def-someuser
  #SBATCH --mem-per-cpu=1.5G
  #SBATCH --time=1:00:00
  ####################################################
  module load gcc/12.3 r/4.4.0
  Rscript script.r
  ```

- Interactive Sessions:

  - [Sockeye](https://confluence.it.ubc.ca/display/UARC/Running+Jobs#RunningJobs-Interactive){target="\_blank"}

  - Alliance

    - Use the Slurm allocation
      ([salloc](https://docs.alliancecan.ca/wiki/Running_jobs){target="\_blank"})
      command

    - Example command for starting session:

      ```bash
      $ salloc --time=00:15:00
      salloc: Pending job allocation 1234567
      ...
      salloc: Nodes cdr<###> are ready for your job
      $ module load gcc/12.3 r/4.4.0
      $ R
      R version 4.4.0 (2024-04-24) -- "Puppy Cup"
      ...
      > <r code here>
      > q()
      Save workspace image? [y/n/c]:
      $ exit
      salloc: Relinquishing job allocation 1234567
      ```

### Other Resources:

- [Introduction to HPC in R Webinar](https://mint.westdri.ca/r/intro_hpc.html){target="\_blank"}

- [High-performance R Tutorial](https://mint.westdri.ca/r/run_r_hpc.html){target="\_blank"}

## Other Supported Languages

- C, C++, Objective-C, and other GCC supported languages

- Elixir (Alliance)

- Go (Alliance)

- Java

- JavaScript/TypeScript via node.js

- Julia

- MATLAB

- Octave

- Perl

- Ruby (Alliance)

- Rust (Alliance)

## Containers on HPC / HTC

- Use Cases:

  - Running software that is not already included as a module on a HPC cluster
    or HTC node

  - Building runtime environments from existing projects and easily reproducing
    research

- Documentation

  - [Alliance](https://docs.alliancecan.ca/wiki/Apptainer){target="\_blank"}

  - [Sockeye](https://confluence.it.ubc.ca/display/UARC/Using+Apptainer+or+Singularity+Containers){target="\_blank"}

- Documentation for HPC Container Platform -
  [Apptainer](https://apptainer.org/docs/user/main/){target="\_blank"}

## Photogrammetry

- [Photogrammetry on HPC Clusters](https://training.westdri.ca/domains/dh/#photogrammetry){target="\_blank"}

Photogrammetry software can be incredibly resource intensive, so running it on
an HPC cluster can save you a lot of time and resources when working with
extraordinarily large datasets.

For an assortment of reasons, most HPC clusters only install free and
open-source software. This includes UBC ARC's Sockeye cluster and the Digital
Research Alliance's clusters. This means that software like Agisoft Metashape,
ArcGIS Drone2Map, and Pix4D are unfortunately not available for use on HPC
clusters.

To leverage HPC clusters for processing drone images or video into orthophotos,
3D models, point clouds, or elevation models,
[Open Drone Map (ODM)](https://docs.opendronemap.org/){target="\_blank"} will
likely be your best option.

ODM is most often distributed within a Docker container, and it can just as
easily run within alternative container engines, like Apptainer or Podman. Prior
to running ODM on an HPC cluster, it is highly recommended that you take a few
test runs on a local machine with a subset of your data. This will give you an
opportunity to explore and optimize any option flags to produce the best results
for your dataset. You can find information on installing Apptainer
[here](https://apptainer.org/docs/admin/main/installation.html#){target="\_blank"}.

To test ODM on a local machine that has Apptainer installed, make a directory
that will be bound to the container for ODM's input and output. Then nest
another directory named 'images' with a subset of your data stored within it.
The example below uses a directory named 'odm_test'.

```bash
$ apptainer run -B odm_test:/project/code docker://opendronemap/odm:latest --project-path /project
```

After processing your dataset, ODM creates a report at
'odm_test/odm_report/report.pdf', which can be used to quickly analyze your
results and start calculating a total job time estimate for your HPC job script.

Once you've identified any flags that you want to add to the command, you will
need to convert the ODM Docker container into an Apptainer SIF container with
the following command on your local machine:

```bash
$ apptainer build odm_latest.sif docker://opendronemap/odm:latest
# For a container with GPU support, run:
# apptainer build odm_gpu.sif docker://opendronemap/odm:gpu
```

Then copy the Apptainer SIF file from your local machine to your HPC home
directory and ensure your dataset is stored in a project directory.

you can use the following in a SLURM job script on the HPC cluster:

```bash
#!/bin/bash
# Include the shebang at the top of the file, to clearly identify that the following script is meant for the Bash Shell
# Provide flags as comments in the script. These will be read by SLURM to set option flags
# Identify your user account
#SBATCH --account=def-someuser
# Identify the amount of CPU cores and memory to allocate the job
#SBATCH --cpus-per-task=20
#SBATCH --mem=64G
#SBATCH --time=5:00:00 # You can use the test runs on your local machine to help you estimate this
# At the beginning of your job load the Apptainer module
module load apptainer
# CPU Only
apptainer run -C -W $SLURM_TMPDIR -B /project/images:/project/code/images,/scratch:/project odm_latest.sif --project-path /project
# For a container with GPU support add the following to the top of your job script along with the following command
#SBATCH --gpu-per-node=1
# apptainer run -C -W $SLURM_TMPDIR -B /project/images:/project/code/images,/scratch:/project --nv odm_gpu.sif --project-path /project
```

The command in the above job script may need to be slightly adjusted based on
the structure of the HPC cluster that you are using with the job script
parameters also being modified to account for the overall size of your dataset.
In general, the above parameters should work well for a dataset of approximately
1000 images[^1]. You can also review the following table to help estimate the
amount of memory to allocate your job based on the size of your dataset.

| Number of Images | RAM or RAM + Swap |
| ---------------- | ----------------- |
| 40               | 4                 |
| 250              | 16                |
| 500              | 32                |
| 1,500            | 64                |
| 2,500            | 128               |
| 3,500            | 192               |
| 5,000            | 256               |

: {.table}

**Source:**
<https://docs.opendronemap.org/installation/#hardware-recommendations>{target="\_blank"}

Based on best practices, you will want to store your dataset within your project
folder and bind the directory holding your dataset to a directory within the
container with the path '/project/code/images'. You will also want to set ODM to
output to your scratch directory by binding it to the ODM project directory.
Finally, flag ODM to use the bound scratch directory as the project output
directory.

Once the job has been completed, you will need to review ODMs output within the
scratch directory and transfer any relevant files back into your project
directory before cleaning up the scratch directory.

[^1]:
    Gbagir, A. G., Ek, K., & Colpaert, A. (2023). OpenDroneMap: Multi-platform
    performance analysis. _Geographies_, 3(3), 446-458.
    <https://doi.org/10.3390/geographies3030023>{target="\_blank"}
