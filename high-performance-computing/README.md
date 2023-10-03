# High Performance Computing

High performance computing can provide a powerful solution when working with
incredibly large datasets as they allow you and your collaborators to run
scripts and programs over those datasets without facing limitations in your
hardware and network speeds. UBC's Advanced Research Computing provides access
to high performance computing via their Sockeye compute cluster along with
secure and redundant digital object storage via Chinook. Additionally, the
Canada-based organization, Digital Research Alliance, provides compute clusters
across Canada, including one located at Simon Fraser University.

- [Introduction to Compute Canada (Alliance) Video](https://www.youtube.com/watch?v=hWkWAaNBILs)

- [Intro to Linux and the Bash Shell in HPC Environments](https://confluence.it.ubc.ca/display/UARC/Introduction+to+Linux+and+Using+the+Command+Line+Interface)

- [Research Computing Bootcamp Videos](https://www.ualberta.ca/information-services-and-technology/research-computing/bootcamps.html?1=HPC)

- [Geospatial Analysis with HPC Video](https://youtu.be/wRmRnVMjKXM)

- [Supercomputing Conference - Recorded Sessions](https://www.youtube.com/@SCconferenceseries/playlists)

- _[Parallel and High Performance Computing](https://go.exlibris.link/1VWhVDjZ)_

## UBC Advanced Research Computing Sockeye

Documentation: <https://confluence.it.ubc.ca/display/UARC/Using+Sockeye>

Supported Software: <https://confluence.it.ubc.ca/display/UARC/Software>

- Note: Linux (CentOS) software can be installed along with conda packages or
  any software available within an Apptainer container

## Digital Research Alliance Clusters

Documentation: <https://docs.alliancecan.ca/wiki/Getting_started>

Supported Software: <https://docs.alliancecan.ca/wiki/Available_software>

- Note: Additionally, any software that is supported on Linux can be ran within
  an Apptainer container

## QGIS

QGIS can run on either UBC Sockeye or Alliance clusters. To interact with QGIS
through a graphical user interface, you'll need to run in it within an
interactive job with X11 forwarding enabled. You can find more information on
creating graphical interactive jobs on UBC Sockeye
[here](https://confluence.it.ubc.ca/display/UARC/Running+Jobs#RunningJobs-GraphicalInteractive),
while documentation for Alliance clusters is listed below.

- [Alliance Documentation - QGIS](https://docs.alliancecan.ca/wiki/QGIS)

## Jupyter

- [Alliance Documentation - JupyterHub](https://docs.alliancecan.ca/wiki/JupyterHub)

- Clusters Running JupyterHub (requires an Alliance account):

  - [Cedar (SFU)](https://jupyterhub.cedar.computecanada.ca/)

  - [Graham (UW)](https://jupyterhub.graham.computecanada.ca/)

  - [Béluga (McGill)](https://jupyterhub.beluga.computecanada.ca/)

  - [Narval (UQ)](https://jupyterhub.narval.computecanada.ca/)

- Supported Kernels (Programming Languages):

  - Python 2.7, 3.6, 3.7, 3.8, 3.9 (default), 3.10, and 3.11

  - R 4.2

  - Julia 1.5 & 1.8

  - Note: Other kernels can be supported using Apptainer containers.

- Server Resource Options:

  - Time (Session Length): 30 minutes - 5 hours

  - Number of (CPU) Cores: 1 - 8

  - Memory (Total Session Limit): 1000MB - 63000MB

  - (Optional) GPU Configuration: none - 4 x V100L

- Note: Nodes do not have internet access, so installing packages from external
  sources, cloning repositories from GitHub, or running code that downloads data
  from external sources will not work. You can only install packages from
  Alliance's maintained set of
  [Python wheels](https://docs.alliancecan.ca/wiki/Available_Python_wheels). To
  run JupyterLab with conda or external libraries held on PYPI, you'll need to
  run it using an Apptainer container as documented in the alternative
  approaches below.

- Alternatives Approaches for Running JupyterLab:

  - [Alliance - Instructions for running JupyterLab via a virtual environment](https://docs.alliancecan.ca/wiki/Advanced_Jupyter_configuration)

  - [UBC ARC Sockeye - Instructions for running JupyterLab via an Apptainer container](https://confluence.it.ubc.ca/display/UARC/Jupyter+Notebooks+with+Singularity)

### Running a Jupyter Kernel from a Container

Containers enable you to pre-build customized environments from which you can
run software that is not supported on the Alliance clusters, and they can be
leveraged to extend the Alliance's JupyterHub clusters by running them as a
custom Jupyter kernels. This can be extraordinarily useful considering Conda is
not supported on the cluster.

Before using this approach, double-check that the software you need is not
already available on the cluster either as
[modules](https://docs.alliancecan.ca/wiki/Available_software) or
[Python wheels](https://docs.alliancecan.ca/wiki/Available_Python_wheels).
Software installed and ran within a container is going to perform less
efficiently than equivalent modules on Alliance, which have been optimized for
HPC.

#### Creating the container environment with Mamba (Conda)

While this can be done within the Alliance login node, it is highly recommended
that the containers are built from another Linux machine and copied onto the
cluster. This will ensure the build runs a bit faster and you aren't competing
for resources with other researchers on the login node.

Note: Whenever you start a new Jupyter server on the cluster, you'll need to
load the apptainer module again in order for the kernel to run.

If you need flexibility in your container, you might be able to create a sandbox
environment from your uploaded container and modify the sandbox container from
your terminal with conda/mamba.

1. Ensure Apptainer is installed on the Linux machine

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

2. Pull the conda-forge/mambaforge Docker container from Docker Hub and build a
   sandbox container from it. This will enable you to use Mamba, an alternative
   to Conda that runs more efficiently in environments where resources are
   limited.

   ```bash
   $ apptainer build --sandbox <container_name>/ docker://condaforge/mambaforge
   ```

3. Start a Bash shell within the sandbox container with write privileges.

   ```bash
   $ apptainer shell --shell /bin/bash --writable <container_name>
   ```

4. Update Mamba.

   ```bash
   Apptainer> mamba update mamba -y
   ```

5. Use Mamba to install the kernel package needed for your preferred programming
   language (Python: ipykernel; R: r-irkernel) and any other packages you need.

   ```bash
   Apptainer> mamba install <kernel_package> <other_packages> -y
   ```

6. Exit the sandbox container shell

   ```bash
   Apptainer> exit
   ```

7. Build your Apptainer container from the sandbox container. Including a time
   stamp with `<container_name>` is recommended when building a container as you
   may want to rebuild the container with updated packages in the future.

   ```bash
   $ apptainer build <container_name>_<timestamp>.sif <container_name>
   ```

#### Installing a Python-Based Container as a Kernel

1. Start a server on the JupyterHub cluster.

2. Start a new terminal.

3. Load the apptainer module.

   ```bash
   $ load module apptainer
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

   ```json
   {
     "argv": [
       "apptainer",
       "exec",
       "/home/<username>/<container_name>.sif",
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
   $ load module apptainer
   ```

4. Close the terminal and start a new one.

5. Using the `nano` text editor, create a new directory and file to store the
   custom Jupyter kernel configuration

   ```bash
   $ nano <container_name>/kernel.json
   ```

   Within the kernel.json file, enter the following:

   ```json
   {
     "argv": [
       "apptainer",
       "exec",
       "/home/<username>/<container_name>.sif",
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
can't use tools like conda and can only use software loaded as modules from the
Alliance. If you need more flexibility for your RStudio session, setup and run
your environment within an Apptainer container as documented below.

### [via Container](https://confluence.it.ubc.ca/display/UARC/RStudio+with+Apptainer)

Note: the linked instructions above cover running RStudio Server on the UBC ARC
Sockeye cluster using Apptainer, but the instructions should be extremely
similar for running on an Alliance cluster as you would just need to convert the
job script from PBS to SLURM.

- Instructions for creating an Apptainer container with pre-installed
  dependencies:

  - Note: You can either build your container on a local Linux system and copy
    the container to the cluster or build it directly on a login node.

  - Example of building an RStudio container on a local Linux (Ubuntu) system

    ```bash
    # Install Apptainer if not already done so
    $ sudo apt update
    $ sudo apt install -y software-properties-common
    $ sudo add-apt-repository -y ppa:apptainer/ppa
    $ sudo apt update
    $ sudo apt install -y apptainer
    # Build a new sandbox container from the Rocker Project RStudio Server Docker container
    $ apptainer build --sandbox rstudio/ docker://rocker/rstudio
    # Run a shell within the sandbox container with write and sudo privileges
    $ apptainer shell --writable --fakeroot rstudio/
    # Start R and install packages
    Apptainer> R
    R version 4.3.1 (2023-06-16) -- "Beagle Scounts"
    ...
    > install.packages('ggplot2')
    ...
    > q()
    Apptainer> exit
    # Convert the sandbox container into a SIF container to be ran on the HPC cluster
    $ apptainer build rstudio.sif rstudio
    ```

## Python

- [Alliance Documentation - Python](https://docs.alliancecan.ca/wiki/Python)

- Supported Versions: 2.7, 3.6, 3.7, 3.8, 3.9, 3.10, and 3.11

- Supported Virtual Environment Managers:

  - UBC ARC Sockeye:

    - conda, virtualenv, and venv

    - [Using Virtual Environments on Sockeye](https://confluence.it.ubc.ca/display/UARC/Using+Virtual+Environments+on+Sockeye)

  - Alliance: virtualenv or venv. conda is not supported, but it can be ran
    using an Apptainer container. In general, Alliance recommends avoiding conda
    and Anaconda packages if possible. Go
    [here](https://docs.alliancecan.ca/wiki/Anaconda/en) for more details. See
    instructions below for creating and running conda from an Apptainer
    container:

    - Creating an Apptainer container with conda and Anaconda packages:

      ```bash
      # Pull the miniconda3 Docker container and create a new sandbox container from it
      $ apptainer build --sandbox conda/ docker://continuumio/miniconda3
      # Run a shell with write access in the sandbox container
      $ apptainer shell --shell /bin/bash --writable conda
      # Update conda
      Apptainer> conda update conda
      # Create a conda environment and install some conda packages
      Apptainer> conda create --name <env_name> <package_names>
      Apptainer> exit
      # Convert the sandbox container into a SIF container
      $ apptainer build conda.sif conda
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
      $ apptainer run -C -B <directory holding Python script> -W $SLURM_TMPDIR conda.sif conda run -n <env_name> python <script>
      ```

- Supported Packages (Alliance):
  <https://docs.alliancecan.ca/wiki/Available_Python_wheels>

  - Note: include `--no-index` flag with `pip` to only install Alliance wheels.
    The Alliance Python wheels have been specifically compiled and optimized to
    run as effectively on HPC clusters as possible.

- Example Job Scripts:

  - SLURM (Alliance):

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

  - PBS (UBC ARC Sockeye with conda):

    1. Prior to running your job, pre-install conda into your job directory and
       recreate your virtual environment

    ```bash
    $ wget https://repo.anaconda.com/miniconda/Miniconda3-py310_23.3.1-0-Linux-x86_64.sh
    $ bash Miniconda3-py310_23.3.1-0-Linux-x86_64.sh
    Welcome to Miniconda3 py310_23.3.1-0
    ...
    $ source ~/.bashrc
    $ conda env create -n venv -f environment.yml
    ```

    2. Create your PBS job script

    ```bash
    #!/bin/bash
    # Include the shebang at the top of the file, to clearly identify that the following script is meant for the Bash Shell
    # Provide flags as comments in the script. These will be read by PBS to set option flags
    # Identify the resource required to run the job
    #PBS -l walltime=1:00:00,select=1:ncpus=1:mem=1.5gb # In this case, I anticipate that the job will take a little less than an hour and that I will only need to use one cluster node and within that node I will need one CPU core with 1.5 GB of memory dedicated to it
    # Identify a name that you can use to identify this job
    #PBS -N my_conda_job
    # Identify your project account
    #PBS -A proj-name
    # Request that the scheduler update you about the status of your job
    #PBS -m abe
    # Provide the scheduler an email address to recieve updates
    #PBS -M your.name@ubc.ca
    ######################################################################################
    # At the beginning of your job, enter your job directory
    cd $PBS_O_WORKDIR
    # Load conda environment
    source ~/.bashrc
    # Activate conda environment
    conda activate venv
    # Add your commands here
    python script.py
    # Deactivate environment
    conda deactivate
    ```

- Interactive Sessions:

  - [Sockeye](https://confluence.it.ubc.ca/display/UARC/Running+Jobs#RunningJobs-Interactive)

  - Alliance

    - Use the Slurm allocation
      ([salloc](https://docs.alliancecan.ca/wiki/Running_jobs)) command

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

- [Working with the Python Dask (Parallelization) Library Video](https://youtu.be/uGy5gT2vLdI)

## R

- [Alliance Documentation - R](https://docs.alliancecan.ca/wiki/R)

- Supported Versions: 4.0, 4.1 & 4.2

- Example Job:

  ```bash
  #!/bin/bash
  #SBATCH --account=def-someuser
  #SBATCH --mem-per-cpu=1.5G
  #SBATCH --time=1:00:00
  ####################################################
  module load gcc/9.3.0 r/4.2.2
  Rscript script.r
  ```

- Interactive Sessions:

  - [Sockeye](https://confluence.it.ubc.ca/display/UARC/Running+Jobs#RunningJobs-Interactive)

  - Alliance

    - Use the Slurm allocation
      ([salloc](https://docs.alliancecan.ca/wiki/Running_jobs)) command

    - Example command for starting session:

      ```bash
      $ salloc --time=00:15:00
      salloc: Pending job allocation 1234567
      ...
      salloc: Nodes cdr<###> are ready for your job
      $ module load gcc/9.3.0 r/4.2.2
      $ R
      R version 4.2.2 (2022-10-31) -- "Innocent and Trusting"
      ...
      > <r code here>
      > q()
      Save workspace image? [y/n/c]:
      $ exit
      salloc: Relinquishing job allocation 1234567
      ```

### Other Resources:

- [Introduction to HPC in R Webinar](https://mint.westdri.ca/r/intro_hpc.html)

- [High-performance R Tutorial](https://mint.westdri.ca/r/run_r_hpc.html)

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

## Containers on HPC

- Use Cases:

  - Running software that is not already included as an HPC module

  - Building runtime environments from existing projects and easily reproducing
    research

- Documentation

  - [Alliance](https://docs.alliancecan.ca/wiki/Apptainer)

  - [Sockeye](https://confluence.it.ubc.ca/display/UARC/Using+Apptainer+or+Singularity+Containers)

- Documentation for HPC Container Platform -
  [Apptainer](https://apptainer.org/docs/user/main/)

## Photogrammetry

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
[Open Drone Map (ODM)](https://docs.opendronemap.org/) will likely be your best
option.

ODM is most often distributed and ran within a Docker container, and it can just
as easily run within alternative container engines, like Apptainer or Podman.
Prior to running ODM on an HPC cluster, it is highly recommended that you take a
few test runs on a local machine with a subset of your data. This will give you
an opportunity to explore and optimize any option flags to produce the best
results for your dataset. You can find information on installing Apptainer
[here](https://apptainer.org/docs/admin/main/installation.html#).

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
# Identify the amount of memory to use per CPU
#SBATCH --mem-per-cpu=1.5G  # In this case the job will only use one CPU with 1.5 GB of memory, adjust as needed
#SBATCH --time=1:00:00 # You can use the test runs on your local machine to help you estimate this
# At the beginning of your job load the Apptainer module
module load apptainer
# CPU Only
apptainer run -C -W $SLURM_TMPDIR -B /project/images:/project/code/images,/scratch:/project odm_latest.sif --project-path /project
# For a container with GPU support, run:
# apptainer run -C -W $SLURM_TMPDIR -B /project/images:/project/code/images,/scratch:/project --nv odm_gpu.sif --project-path /project
```

The command in the above job script may need to be slightly adjusted based on
the structure of the HPC cluster that you are using with the job script
parameters being also being modified to account for the overall size of your
dataset.

Based on best practices, you will want to store your dataset within your project
folder and bind the directory holding your dataset to a directory within the
container with the path '/project/code/images'. You will also want to set ODM to
output to your scratch directory by binding it to the ODM project directory.
Finally, flag ODM to use the bound scratch directory as the project output
directory.

Once the job has been completed, you will need to review ODMs output within the
scratch directory and transfer any relevant files back into your project
directory before cleaning up the scratch directory.
