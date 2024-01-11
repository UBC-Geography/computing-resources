---
title: Getting Started with Conda, Virtual Environments, and Python
---

There are many different ways to install and start using Python on your personal
device, and no one way is the correct way. How one installs Python often simply
comes down to personal preference. In general, we recommend using a tool called
Conda. When performing geospatial computing, you'll likely be working with
multiple projects that depend on not only Python but other languages too, like
R, Julia, or JavaScript. You may also find that you projects can't always run on
the same exact version of Python. Conda enables you to easily install and run
multiple versions of Python along with a range of other languages and software
packages.

## Conda

Just as there is with Python, there are multiple ways to install Conda. We
recommend using the latest
[Miniconda installer](https://docs.conda.io/en/latest/miniconda.html#latest-miniconda-installer-links).

Conda's documentation includes installation instructions for Windows, MacOS, and
Linux
[here](https://conda.io/projects/conda/en/stable/user-guide/install/index.html#regular-installation).

Once you have Conda installed on your machine, follow along with
['Getting Started With Conda'](https://conda.io/projects/conda/en/stable/user-guide/getting-started.html)
to familiarize yourself with some of Conda's basic functionalities.

## Virtual Environments

Along with being a package manager, which makes installing and managing
software, significantly more convenient, Conda also acts as an environment
manager. Before getting started with using Conda and Python, it's important to
have an understanding of virtual environments and how Conda works with them to
install software and packages onto your machine. If you followed along with the
[Managing Environments](https://conda.io/projects/conda/en/stable/user-guide/getting-started.html)
section of 'Getting Started With Conda', then you got a very basic introduction
to creating and using a virtual environment.

Let's walkthrough the process again by creating a virtual environment that has
JupyterLab installed. We could then install some extensions and other packages
into this environment and clone it in the future as we start new projects in
order to save ourselves a little bit of time.

To start, you will need to open a terminal on your machine. If you are using
Windows, the Conda installer would have added a new application to your machine
named Anaconda Prompt. Running this application is the recommended approach to
starting a terminal and running Conda.

Before we can start installing Conda packages, we will need to create our new
virtual environment. We will name it `jupyter`.

```bash
$ conda create --name jupyter
```

Next we'll want to activate the `jupyter` virtual environment so we can start
interacting with it and installing our packages into it.

```bash
$ conda activate jupyter
```

When you activate a virtual environment, the name of the environment will be
prepended to your shell prompt, like so:

```bash
(jupyter) $
```

Now that we have our virtual environment activated, we can install JupyterLab
along with all of its dependencies.

```bash
(jupyter) $ conda install --channel conda-forge jupyterlab
```

JupyterLab has a decent number of dependencies, one of which is Python. You will
notice that Conda lists those dependencies and asks if you want to proceed with
installing them along with Python. This is a good time to ensure you did not
enter the install command with a typo and are about to accidentally install the
wrong package. If everything looks correct, respond to the prompt to proceed.

Every package that you install with Conda includes information within it that
lists all of its dependent packages and the range of versions that it will be
compatible with. We can use Conda to review what dependencies were included with
JupyterLab and which version of Python has been installed within the
environment.

```bash
(jupyter) $ conda list
# packages in environment at ...\miniconda3\envs\jupyter:
#
# Name      Version       Build                 Channel
anyio       3.7.1         pyhd8ed1ab_0          conda-forge
...
python      3.10.12       h4de0772_0_cpython    conda-forge
...
zipp        3.16.0        pyhd8ed1ab_1          conda-forge
```

You will notice that I have abbreviated the list quite a bit with ellipses, but
I can see that JupyterLab included Python 3.10.12 as a dependency for me. You
may see a newer version listed when you run this command. In a later step, we
will look at how we can upgrade or downgrade Python to another version that
remains compatible with JupyterLab.

Okay, let us get JupyterLab up and running, with the following command:

```bash
(jupyter) $ jupyter lab
```

If everything worked correctly, you will notice a new browser window has opened
with JupyterLab up and ready to go and the shell in your terminal has started
logging information from JupyterLab. Let us minimize our terminal for now to let
it continue logging info, and we will jump into a new terminal session within
JupyterLab. Because we are running JupyterLab within our virtual environment, we
will not actually see the environment name prepended to the terminal prompt as
we did before, but we can be confident that the virtual environment is activated
within our terminal. If we wanted to double-check, we could always run the
following command to list our virtual environments:

```bash
$ conda info --envs
# conda environments:
#
base                     C:\Users\user\miniconda3
jupyter               *  C:\Users\user\miniconda3\envs\jupyter  # The * notifies us that 'jupyter' is the currently active environment
```

MacOS and Linux users will see different paths listed for the locations of their
virtual environments.

From here, you can continue using Conda to install any other packages that you
want within this environment. You could add R, Julia and their accompanying
kernel packages along with some helpful JupyterLab extensions, like
`jupyterlab-git` or `jupyterlab-github`. You can also use Python's built-in
package manager to install packages that are available from the Python Package
Index (PyPI). Consider installing packages that you think would be useful in all
of your projects.

Now that we have setup our basic JupyterLab environment, we can clone the
environment to start working on a new project, where we will install packages
that are specific to that project. First, we will shutdown our JupyterLab and
return to our original terminal. Then we will run the following commands to
deactivate our `jupyter` environment and clone it to create a new environment
named `geog`

```bash
(jupyter) $ conda deactivate
$ conda create -n geog --clone jupyter
```

While cloning can be helpful for quickly copying a virtual environment on your
local machine, it is not going to be much help if you want to share a virtual
environment with someone else or transfer it to a different machine. To make the
process easy, Conda includes the ability to take a snapshot of all the packages
installed within an environment and store the name and versions of those
packages into a text-based YAML (.yml) file using the following command.

```bash
$ conda activate jupyter
(jupyter) $ conda env export > jupyter_environment.yml
```

Let us make one more environment using the environment file that we just created
to see how it works, and we will just list our environments again to verify that
it was created.

```bash
(jupyter) $ conda deactivate
$ conda env create -n testenv -f jupyter_environment.yml
$ conda info --envs
# conda environments:
#
base                   * C:\Users\user\miniconda3
geog                     C:\Users\user\miniconda3\envs\geog
jupyter                  C:\Users\user\miniconda3\envs\jupyter
testenv                  C:\Users\user\miniconda3\envs\testenv
```

Next let us just do a little cleanup by removing the `testenv` environment that
we just created and verify that it is no longer on our machine.

```bash
$ conda remove -n testenv --all
$ conda info --envs
# conda environments:
#
base                   * C:\Users\user\miniconda3
geog                     C:\Users\user\miniconda3\envs\geog
jupyter                  C:\Users\user\miniconda3\envs\jupyter
```

## Python

Now I want to return to my `geog` environment, and rather than running Python
3.10.12, which was installed as a dependency with JupyterLab, I want to run the
latest Python release available. We can use the following commands to activate
the `geog` environment and then use Conda's search tool to see what Python
versions are available.

```bash
$ conda activate geog
(geog) $ conda search --channel conda-forge python
Loading channels: done
#Name               Version         Build           Channel
python              2.7.12          0               conda-forge
...
python              3.11.4          he1021f5_0      pkgs/main
```

You will notice that I have abbreviated the list quite a bit with an ellipsis,
but I currently have access to a range of Python versions from 2.7.12 to 3.11.4.

Now which Python version you install will heavily depend on the other packages
and software that you intend to use within your environment. You will need to
take a close look at what Python versions the packages that you want to use are
compatible with.

At the time of writing this, the default Python version installed with
JupyterLab, 3.10.12, would actually be the best option. It is usually a good
choice to select one minor version older than the newest version of Python
(currently 3.11.4). This ensures a broader level of compatibility with a range
of packages. For many package maintainers, it can be quite a bit of work to
update their code to make it compatible with the latest minor release of Python,
so we can account for this by using an earlier minor release.

Today, I am feeling a bit adventurous though, and I want to to see if I can
install a newer version of Python in my `geog` environment. I will run the
following command to update Python to the latest version compatible with
JupyterLab and all of its other dependencies.

```bash
(geog) $ conda update --channel conda-forge python
```

And voilà, I have Python 3.11.4 installed and ready to go. A newer version of
Python 3.11 may have been released since writing this, so you might actually see
a newer version installed in your environment.
