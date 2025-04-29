---
title: Running Isca
# change to date to last-modified after next modification
date: 2025-04-17
---

::: {.callout-warning}

## Warning

This page is still a draft and requires further review.

:::

> Isca is a framework for the idealized modelling of the global circulation of
> planetary atmospheres at varying levels of complexity and realism. The
> framework is an outgrowth of models from GFDL designed for Earth's atmosphere,
> but it may readily be extended into other planetary regimes. Various forcing
> and radiation options are available, from a dry Newtonian relaxation to a
> moist dynamics with full radiation.

This page provides a tutorial on how to run
[Isca](https://execlim.github.io/Isca/) in an HTC/HPC environment using either
UBC ARC's Sockeye cluster or one of the Alliance clusters. It's been adapted
from both
[Isca's README - Getting Started](https://github.com/ExeClim/Isca?tab=readme-ov-file#getting-started)
and
[William Seviour's Guide to Running Isca on the University of Bristol's BlueCrystal Phase 4](https://github.com/wseviour/Bristol_Climate_Dynamics/blob/master/Isca_SOCRATES.md#guide-to-running-isca-with-socrates-on-bluecrysal-phase-4).
This guide is relatively technical and has the following requirements:

- Status as faculty or a librarian with an institution that holds eligibility
  for CFI grants
- An account on either UBC ARC Sockeye or the Alliance
- Working knowledge of UNIX/Linux

1. Isca has been built using both Python and Fortran, and to run, it requires
   both a Fortran compiler and a Python virtual environment. To enable Isca to
   run more efficiently and ensure reproducibility, an important first steps is
   to generate a new requirements.txt file. This file will then be used to
   consistently rebuild a virtual environment each time you run Isca.

   ::: {.panel-tabset}

   ## Sockeye

   ```bash
   # Load the Alliance software stack
   $ module load CVMFS_CC
   # Load the Python module
   $ module load python/3.12
   # Upgrade pip
   $ python -m pip install --no-index --upgrade pip
   # Pre-download the f90nml package from PYPI
   $ python -m pip download --no-deps f90nml
   # Create a temporary virtual environment
   $ ENVDIR=/tmp/$RANDOM
   $ virtualenv --no-download $ENVDIR
   # Activate the environment
   $ source $ENVDIR/bin/activate
   # Install the dependency packages
   $ python -m pip install f90nml-<version>.tar.gz
   $ python -m pip install --no-index sh jinja2 numpy pandas xarray tqdm
   # Export a requirements.txt file with packages
   $ python -m pip freeze --local > ~/.isca/requirements.txt
   # Deactivate and delete the temporary environment
   $ deactivate
   $ rm -rf $ENVDIR
   ```

   ## Alliance

   ```bash
   # Load the Python module
   $ module load python/3.12
   # Upgrade pip
   $ python -m pip install --no-index --upgrade pip
   # Pre-download the f90nml package from PYPI
   $ python -m pip download --no-deps f90nml
   # Create a temporary virtual environment
   $ ENVDIR=/tmp/$RANDOM
   $ virtualenv --no-download $ENVDIR
   # Activate the environment
   $ source $ENVDIR/bin/activate
   # Install the dependency packages
   $ python -m pip install f90nml-<version>.tar.gz
   $ python -m pip install --no-index sh jinja2 numpy pandas xarray tqdm
   # Export a requirements.txt file with packages
   $ python -m pip freeze --local > ~/.isca/requirements.txt
   # Deactivate and delete the temporary environment
   $ deactivate
   $ rm -rf $ENVDIR
   ```

   :::

2. Next, clone the Isca repository from GitHub into your home directory. If you
   are working with collaborators in a project directory, that might be a better
   location to clone the Isca repository into as that will ensure everyone is
   using the same source code.

   ```bash
   $ git clone https://github.com/ExeClim/Isca.git
   ```

3. If you were previously running Isca on a local workstation, you were likely
   using `conda` to setup and install Isca's environment While that workflow may
   still work in Sockeye or on one of the Alliance clusters, switching away from
   `conda` and `conda-forge` packages to Alliance provided modules and Python
   wheels could provide some very easy performance improvements. Isca itself
   already provides a standard method for porting to different environments
   through the environment files stored in the `Isca/src/extra/env` directory.
   By setting the GFDL_ENV environment variable, you can swap out environments
   as needed. You can also create your own local environments, which is the
   method used in this tutorial.

   ::: {.panel-tabset}

   ## Sockeye

   ```bash
   $ nano .isca/intel_sockeye
   ```

   ```{.sh filename="~/.isca/intel_sockeye"}
   echo loadmodules for sockeye

   module purge
   module load CVMFS_CC
   module load intel/2024.2.0
   module load openmpi/5.0.3
   module load hdf5-mpi/1.14.5
   module load netcdf-fortran-mpi/4.6.1

   export F90=mpifort
   export CC=mpicc
   ```

   ## Alliance

   ```bash
   $ nano .isca/intel_alliance
   ```

   ```{.sh filename="~/.isca/intel_alliance"}
   echo loadmodules for alliance clusters

   module purge
   module load intel/2024.2.0
   module load openmpi/5.0.3
   module load hdf5-mpi/1.14.5
   module load netcdf-fortran-mpi/4.6.1

   export F90=mpifort
   export CC=mpicc
   ```

   :::

4. Modify your `.bashrc` file to set Isca's environment variables

   ```bash
   $ nano ~/.bashrc
   ```

   ::: {.panel-tabset}

   ## Sockeye

   ```{.sh filename="~/.bashrc"}
   # directory of the Isca source code
   export GFDL_BASE=$HOME/Isca
   # "environment" configuration for use with Sockeye
   export GFDL_ENV=$HOME/.isca/intel_sockeye
   # temporary working directory used in running the model
   export GFDL_WORK=/scratch/<alloc-code>/isca_work
   # directory for storing model output
   export GFDL_DATA=/scratch/<alloc-code>/isca_data
   ```

   ## Alliance

   ```{.sh filename="~/.bashrc"}
   # directory of the Isca source code
   export GFDL_BASE=$HOME/Isca
   # "environment" configuration for use with Alliance clusters
   export GFDL_ENV=$HOME/.isca/intel_alliance
   # temporary working directory used in running the model
   export GFDL_WORK=/scratch/<username>/isca_work
   # directory for storing model output
   export GFDL_DATA=/scratch/<username>/isca_data
   ```

   :::

5. Create a new SLURM job script

   ```bash
   $ nano isca_slurm_job.sh
   ```

   ::: {.panel-tabset}

   ## Sockeye

   ```{.sh filename="isca_slurm_job.sh"}
   #!/bin/bash
   #SBATCH --job-name=test_case     # Specify the job name
   #SBATCH --account=<your-alloc>   # Specify your allocation code
   #SBATCH --time=1:00:00           # Request 1 hour of runtime
   #SBATCH --nodes=1                # Request 1 node
   #SBATCH --ntasks-per-node=16     # Request 16 tasks
   #SBATCH --mail-user=<your-email> # Email address for job notifications
   #SBATCH --mail-type=ALL          # Receive email notifications for all job events

   # Load environment variables
   source ~/.bashrc
   # Load Python
   module load CVMFS_CC
   module load python/3.12
   # Create and activate a temporary virtual environment
   virtualenv --no-download $SLURM_TMPDIR/env
   source $SLURM_TMPDIR/env/bin/activate
   # Upgrade pip and install dependencies
   python -m pip install --no-index --upgrade pip
   python -m pip install --no-index -r $HOME/.isca/requirements.txt
   # Install the Isca front-end
   python -m pip install -e $GFDL_BASE/src/extra/python
   # Run the test case
   python $GFDL_BASE/exp/test_cases/held_suarez/held_suarez_test_case.py
   ```

   ## Alliance

   ```{.sh filename="isca_slurm_job.sh"}
   #!/bin/bash
   #SBATCH --job-name=test_case     # Specify the job name
   #SBATCH --account=<your-alloc>   # Specify your allocation code
   #SBATCH --time=1:00:00           # Request 1 hour of runtime
   #SBATCH --nodes=1                # Request 1 node
   #SBATCH --ntasks-per-node=16     # Request 16 tasks
   #SBATCH --mail-user=<your-email> # Email address for job notifications
   #SBATCH --mail-type=ALL          # Receive email notifications for all job events

   # Load environment variables
   source ~/.bashrc
   # Load Python
   module load python/3.12
   # Create and activate a temporary virtual environment
   virtualenv --no-download $SLURM_TMPDIR/env
   source $SLURM_TMPDIR/env/bin/activate
   # Upgrade pip and install dependencies
   python -m pip install --no-index --upgrade pip
   python -m pip install --no-index -r $HOME/.isca/requirements.txt
   # Install the Isca front-end
   python -m pip install -e $GFDL_BASE/src/extra/python
   # Run the test case
   python $GFDL_BASE/exp/test_cases/held_suarez/held_suarez_test_case.py
   ```

   :::

6. Submit your job

   ```bash
   $ sbatch isca_slurm_job.sh
   ```

7. Once the job has finished review the output in the scratch directory and copy
   any relevant data to either your home or project directory for retention.
