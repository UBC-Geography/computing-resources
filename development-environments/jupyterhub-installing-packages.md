---
title: Installing Packages in UBC LT's Jupyter Open or UBC Syzygy
---

When using one of UBC's remote Jupyter services, you will likely find that
JupyterHub's default environment does not include a range of packages needed to
complete your research. While it is possible to install more packages within the
default environment using package managers like, Pip, Conda, or Mamba, you may
find yourself running into instances where you need to run an unsupported
version of Python or R and/or need to install packages that conflict with the
packages already included in the default environment. The following instructions
provide walkthrough documentation for installing new packages and creating
customized kernels within a JupyterHub environment.

If you need to share a reproducible Jupyter environment or would like to
automate the creation and management of your kernels, copy the Makefile from
this [repository](https://github.com/UBC-Geography/jupyter-makefile) into your
project and follow the instructions found in the repository's README.

## Mamba

If you are simply running into issues with installing packages via Conda, try
using Mamba instead. Mamba is a fast and lightweight alternative to Conda that
is already included in JupyterHub's default environment. It runs more
efficiently in computing environments with fewer resources, such as
[UBC LT's Jupyter Open](https://open.jupyter.ubc.ca/) or
[UBC Syzygy](https://ubc.syzygy.ca/).

## Virtual Environments

While installing new packages within the default environment can initially seem
quite convenient. You can often run into issues when attempting to install a
package that shares a dependency with one of the packages already installed in
the default environment. You will also find that packages that are installed
within the default environment do not persist between sessions, requiring you to
re-install them whenever you start a new Jupyter session. It is important to
note that the default environment does not only contain a set of packages that
JupyterHub administrators thought would be frequently useful to users, it also
contains packages that run the Jupyter user interface (JupyterLab) and the
pre-installed Jupyter kernels. To avoid some of those issues, such as conflicts
between package dependencies, you can use virtual environments, which help to
isolate your computing environment from the default environment thus enabling
you to more freely install, manage, and persist your packages.

The following instructions use Mamba as a drop in replacement for Conda and can
be used for setting up either Python or R-based environments.

1.  Navigate to your preferred JupyterHub service, start a new Jupyter server,
    and launch a terminal.

2.  From the terminal, create a new virtual environment and install the
    appropriate kernel package. Replace `<environment_name>` with a unique name
    that can be used to easily identify your environment, like a project name.
    The name will be used to create a new directory in your Home directory, so
    avoid including any spaces.

    Python:

    ```bash
    $ mamba create -p <environment_name> ipykernel -y
    ```

    R:

    ```bash
    $ mamba create -p <environment_name> r-irkernel -y
    ```

3.  Before you can activate your virtual environment and start installing
    packages within it, you will need to initialize Mamba and restart your Bash
    shell.

    ```bash
    $ mamba init -q && source ~/.bashrc
    ```

4.  Next switch from the default environment to your newly created virtual
    environment by activating it. Replace `<username>` with the username
    displayed in the terminal's shell prompt. On Open Jupyter, this would be
    `jovyan`, while on UBC Syzygy, it would be your CWL username. And again
    replace `<environment_name>` with the name you used earlier in Step 2.

    ```bash
    $ mamba activate /home/<username>/<environment_name>
    ```

5.  Now you can begin installing your packages into the virtual environment.

    ```bash
    $ mamba install <package_names> -y
    ```

    Note: Some packages that you need may not be available via Mamba's default
    package repository, conda-forge, and are only available from the Python
    Package Index (PyPI) or the Comprehensive R Archive Network (CRAN). To
    install those packages, you can use Python's `pip` or R's
    `install.packages()` with one of the following commands:

    ```bash
    $ python -m pip install <python_package_names>
    ```

    ```bash
    $ Rscript -e 'install.packages(c("<r_package_names>"),repo="https://mirror.rcg.sfu.ca/mirror/CRAN/",quiet=TRUE)'`
    ```

6.  With your virtual environment setup and still active, you will need to
    register the environment as a Jupyter kernel using the kernel packages
    installed during the creation of your environment to make it available to
    your notebooks.

    Python:

    ```bash
    $ python -m ipykernel install --user --name <environment_name> --display-name "Python (<environment_name>)"
    ```

    R:

    ```bash
    $ Rscript -e 'IRkernel::installspec(name="<environment_name>", displayname="R (<environment_name>)")'`
    ```

After a few seconds, the custom kernel built from you virtual environment will
be listed in the JupyterLab launcher and you will be able to select it as the
preferred kernel to run within your notebooks.

To install more packages into your environment, repeat Steps 3-5 from a
JupyterLab terminal.

It is important to note that the directories created for each virtual
environment can be quite large as more packages are installed within them.
Consider purging the environments when they are no longer needed and remember to
include the directory in your `.gitignore` file if you are using Git/GitHub.

You can purge an environment from JupyterHub by completing the following steps:

1. Open a JupyterLab terminal.

2. Remove the kernel from Jupyter.

   ```bash
   $ jupyter kernelspec remove <environment_name> -y
   ```

3. Remove the virtual environment.

   ```bash
   $ mamba remove -p /home/<username>/<environment_name> --all
   ```
