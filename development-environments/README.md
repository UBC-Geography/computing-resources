---
output-file: index.html
title: Development Environments
date: last-modified
---

A development environment can often encompass both a code editor or integrated
development environment (IDE) and the software necessary to compile and/or run
code for debugging and testing purposes. Setting up a development environment is
usually an important first step when getting started with a new programming
language.

Most geographers rely on programming languages that are interpreted rather than
compiled. Meaning they have to install software that includes a runtime
environment that can run their code along with any open-source packages that
their code depends on. Packager managers and virtual environment managers or
tools that provide a combination of both, like `mamba`, are extremely important
for easing the process of setting up a development environment and ensuring that
code can be shared with reproducible results.

## Coding Playgrounds

Coding playgrounds are often used for instruction as well for testing code ideas
on the fly. They essentially provide access to a pre-built development
environment that runs a code editor or IDE in the user's web browser while
feeding code to a runtime environment that's been installed on an isolated
allotment of computing resources on a remote server.

### JupyterHub

The easiest way for a UBC faculty and student to access a development
environment is through a JupyterHub service, like
[UBC LT's Open Jupyter](https://open.jupyter.ubc.ca/){target="\_blank"} or
[UBC Syzygy](https://ubc.syzygy.ca/){target="\_blank"}. Both playgrounds enable
users to connect to and interact with Jupyter Notebooks without having to
install anything on their own machines. While convenient, these services come
with significant drawbacks in computing power and will not work well in cases
where computations are running on large datasets. For more intensive
computational work either run
[JupyterLab](https://ubc-geography.github.io/computing-resources/development-environments/#jupyterlab)
on your local machine or access a
[JupyterHub instance running on one of the Alliance's HPC clusters](https://ubc-geography.github.io/computing-resources/high-performance-computing/#jupyter){target="\_blank"}.

#### UBC Open Jupyter

- [UBC LT - JupyterHub Instructor Guide](https://lthub.ubc.ca/guides/jupyterhub-instructor-guide/){target="\_blank"}

Resources Per User:

- 1 CPU
- 2.5 GB RAM
- 10 GB Storage

Supported Software:

- Python 3.11.10
- R 4.3.3
- Julia 1.11.1
- An assortment of pre-installed Python and R packages

UBC LT provides access to a large collection of software within their JupyterHub
instance, Open Jupyter, but many core geospatial packages are not currently
installed in the environment. Review
[JupyterHub - Installing Packages](https://ubc-geography.github.io/computing-resources/development-environments/jupyterhub-installing-packages.html){target="\_blank"}
for instructions on setting up alternative Jupyter kernels and installing
additional packages.

#### UBC Syzygy

- [Introduction to Syzygy - First Steps](https://intro.syzygy.ca/first-steps/){target="\_blank"}

Resources Per User:

- 0.5 CPU
- 2 GB RAM
- 1 GB Storage

Supported Software:

- Python 3.12.8
- R 4.4.1
- GDAL 3.9.1
- PROJ 9.4.1
- GEOS 3.12.1
- An assortment of pre-installed Python and R packages

### JupyterLite

As an experimental alternative to JupyterHub, JupyterLite similarly runs
JupyterLab, but rather than allocate resources on a remote server, JupyterLite
leverages WebAssembly (WASM) to install runtime environments and various
packages directly in the user's web browser alongside JupyterLab.

UBC Geography has setup an experimental deployment of JupyterLite. This is the
fastest and easiest method for accessing a local instance of JupyterLab, but
it's also the least stable and lacks many of the same features that would be
included in an instance that's either running on JupyterHub or has been
installed locally via `pip` or `mamba`, so it's best used in more limited use
cases.

- [UBC Geography JupyterLite](https://ubc-geography.github.io/jupyterlite){target="\_blank"}

### Google Earth Engine

Providing a code editor, a basic JavaScript runtime environment, and access to a
massive collection of remote sensing data via a well-documented API, Google
Earth Engine is a highly-specialized coding playground for running complex
analysis on the GEE datasets. To get started, researchers, instructors, and
students will need a Google account and a noncommercial Google Cloud Project,
which can be setup [here](https://code.earthengine.google.com/register).
[JavaScript - GEE](https://ubc-geography.github.io/computing-resources/javascript/#google-earth-engine-gee)
provides resources for getting started with GEE through the code editor and API.

## Virtual Environment Managers

Virtual environments are an important tool for isolating multiple Python
projects on a single machine, and their use is highly recommended when starting
new projects. By isolating your projects, you can ensure that each project is
only using the specific Python packages that were identified and installed for
running it. This makes the project easier to reproduce while also reducing
errors caused by clashing package dependencies.

For a very helpful introduction to virtual environments, check out the
[Environments Tutorial](https://eoas-ubc.github.io/tut-conda_environs.html){target="\_blank"}
from the
[Opensource Computing for Earth Science Education (OCESE) Project](https://eoas-ubc.github.io/index.html){target="\_blank"}.

- UBC ARC - Virtual Environment 2023 - Videos:
  [Part 1 (virtualenv)](https://youtu.be/fdMNwQu8MKU?si=Fu_JogcK_SxEsBiC){target="\_blank"}
  &
  [Part 2 (conda)](https://youtu.be/BrZ_5rP4b0g?si=GkDWSa9CG5z1uqYx){target="\_blank"}

- [Getting Started with Conda, Virtual Environments, and Python](https://UBC-Geography.github.io/development-environments/conda-getting-started){target="\_blank"}

### Conda and Mamba

`conda` and it's faster alternative, `mamba`, are extremely powerful tools for
both managing virtual environments and packages. Using `conda install` provides
the ability to install a range of packages that either aren't available or can't
be installed via Python's built-in package manager, Pip. Additionally, Conda
enables you to install and manage multiple versions of Python or a range of
other programming languages on a single machine using virtual environments.

- [Conda User Guide](https://docs.conda.io/projects/conda/en/stable/user-guide/index.html){target="\_blank"}

- [Mamba User Guide](https://mamba.readthedocs.io/en/latest/user_guide/mamba.html){target="\_blank"}

If you need to install `mamba` and `conda` on your device, we suggest using the
link below to install it using the Miniforge installer.

- [Miniforge](https://github.com/conda-forge/miniforge){target="\_blank"}

### Python - venv and virtualenv

venv is a lightweight module that has been included with base installations of
Python since version 3.3 and enables you to quickly setup and manage virtual
environments for your project. virtualenv is a more powerful alternative to
venv, but unlike venv it needs to be installed separately via pip. Both modules
lack the same level of functionality as conda, but they can be helpful tools for
those who are still getting comfortable with Python or don't need conda's added
functionalities.

- [venv Documentation](https://docs.python.org/3/library/venv.html){target="\_blank"}

- [virtualenv Documentation](https://virtualenv.pypa.io/en/latest/){target="\_blank"}

### R - renv

R's equivalent to virtualenv is renv, which itself is a successor to another
R-based virtual environment manager, packrat. renv has been developed by the
same team behind RStudio and it's usage is recommended within the RStudio user
guide.

- [Introduction to renv](https://rstudio.github.io/renv/articles/renv.html){target="\_blank"}

- [RStudio User Guide - renv](https://docs.posit.co/ide/user/ide/guide/environments/r/renv.html){target="\_blank"}

## Integrated Development Environments (IDE) and Code Editors

### Jupyter

Project Jupyter consists of an ecosystem of open-source projects that support
the creation and distribution of computational notebooks. While Jupyter supports
computational notebooks with kernels from a wide range of programming languages,
it specializes in Python while also providing strong support for R and Julia.
Much of the Jupyter ecosystem has been written in and/or runs on Python.

For those just getting started with Jupyter, UBC's COMET Project has developed a
great
[tutorial](https://comet.arts.ubc.ca/docs/1_Getting_Started/getting_started_intro_to_jupyter/getting_started_intro_to_jupyter.html){target="\_blank"}
on creating and editing computational notebooks through JupyterLab.

For an in-depth walkthrough of the entire Project Jupyter ecosystem, review the
[Jupyter Tutorial](https://jupyter-tutorial.readthedocs.io/en/latest/index.html){target="\_blank"}.

#### Jupyter Notebooks

The term Jupyter Notebooks is used interchangeably to refer to the Jupyter
Notebook file format for computational notebooks and the user interface that has
most commonly been to used to author and edit them. In recent years, the Project
Jupyter team has slowly encouraged users to migrate from the classic Jupyter
Notebook interface to JupyterLab, its more feature-rich successor.

- [Jupyter Notebook (File) Format Documentation](https://nbformat.readthedocs.io/en/latest/index.html){target="\_blank"}

- [Jupyter Notebook (User Interface) Documentation](https://jupyter-notebook.readthedocs.io/en/latest/index.html){target="\_blank"}

#### JupyterLab

You can install and run JupyterLab on your local machine in three separate ways.
The traditional and most flexible approach is to install JupyterLab as a Python
package using `pip`, `conda`, or `mamba` and starting it from the Jupyter
command line interface. We recommend the latter using the following commands to
create a new environment and install Jupyter along with it's dependencies within
that environment.

```bash
$ mamba create -n jupyter jupyterlab -y
```

Then activate the Jupyter environment and start Jupyter Lab.

```bash
$ mamba activate jupyter
(jupyter) $ jupyter lab
```

This will fire up a Jupyter server and open the JupyterLab interface directly in
your web browser.

- [JupyterLab Documentation](https://jupyterlab.readthedocs.io/en/latest/index.html){target="\_blank"}

For those who may be uncomfortable with installing Python and/or using command
line interfaces, Project Jupyter has also released a simple-to-use desktop
application, named JupyterLab Desktop. This application comes packaged with
Python and a default set of packages that are frequently used in scientific
computing.

- [JupyterLab Desktop - Installation](https://github.com/jupyterlab/jupyterlab-desktop#installation){target="\_blank"}

- [JupyterLab Desktop User Guide](https://github.com/jupyterlab/jupyterlab-desktop/blob/master/user-guide.md){target="\_blank"}

#### Jupyter Kernels

Jupyter uses the term kernel to refer to separate programming languages with
their own interactive shells. It's not uncommon to have multiple projects
running in different programming languages. This is where kernels can come in
handy as they enable you to have multiple, isolated computing environments
available within a single IDE.

When you installed JupyterLab with `mamba`, it came with its own preferred
version of Python on which it is dependent. This installation of Python is
immediately added as your default Jupyter kernel.

and for R it is `r-irkernel`. You can find a comprehensive list of packages for
various programming languages
[here](https://github.com/jupyter/jupyter/wiki/Jupyter-kernels){target="\_blank"}.

##### Python

You are more than welcome to start installing Python packages into the Jupyter
virtual environment to make them available to the default Python kernel and the
Jupyter notebooks that are running off that kernel, but we recommend taking the
additional step of installing another kernel that runs in a separate environment
from Jupyter. Yes, that means that you'll have at least three different
installations of Python running on your machine if you are using and that might
feel a bit redundant, but the additional isolation and flexibility will be well
worth it as they'll ensure that you can customize your Jupyter environment with
all the extensions you want alongside a Python environment that can run any
package you need on whatever Python version you want (only stable and maintained
versions please). This comes with the added benefit of being able to export and
share your conda environment and ensuring that those you share it with only
install the packages that they need to run your code.

Open a new terminal either in JupyterLab or a shell environment with access to
`mamba`. Then create a new virtual environment with the version of Python that
you'd like to install along with `ipykernel`.

```bash
$ mamba create -n python_env python=3.12 ipykernel -y
```

Next, use `ipykernel` to install the virtual environment as a Jupyter kernel.

```bash
$ mamba run -n python_env python -m ipykernel install --user --name python_env --display-name "Python (python_env)"
```

Launch JupyterLab, if it isn't already running, and you should see the
python_env environment listed as a kernel in the launcher.

##### R

Similar to Python, you have the option of running an R kernel within the same
environment as Jupyter or from an entirely separate one. Unfortunately, setting
up an R kernel can be a little more complex, so the recommended approach is to
run your R kernels alongside Jupyter within their own separate virtual
environments. This loses some of the convenience of operating within a single
JupyterLab setup or alternatively running within an R-centered IDE, like
RStudio, but it comes with the key benefit of enabling your R code to be shared
in a larger Jupyter-based ecosystem.

```bash
$ mamba create -n r_env r-base r-irkernel jupyter -y
$ mamba run -n r_env Rscript -e "IRkernel::installspec(name='r_env',displayname='R (r_env)')"
$ mamba run -n r_env jupyter lab
```

If you are keen to attempt to add an R kernel to an exiting Jupyter environment
and don't mind running into a few issues, you can try the following set of
commands.

Create your R-based conda environment, which will be hosting the kernel, and
activate it.

```bash
$ mamba create -n r_env r-base r-irkernel -y
$ mamba activate r_env
```

Then from a Bash environment copy the kernelspec directory that is included with
the r-irkernel package. This directory holds a default kernel config that is
used when installing kernels in Jupyter.

```bash
$ cp -r $CONDA_PREFIX/lib/R/library/IRkernel/kernelspec r_env_kernel
```

First run one `sed` command on the Jupyter kernel config file that replaces the
command that starts the default installation of R with a command that points to
the installation of R running in your virtual environment.

::: {.panel-tabset}

## Windows

Be sure to replace `<user_name>` with your Windows username.

```bash
$ sed -i 's/"R", /"C:\\\\Users\\\\<user_name>\\\\miniforge3\\\\Scripts\\\\mamba.exe", "run", "-n", "r_env", "R", /' r_env_kernel/kernel.json
```

## Mac OS or Linux

```bash
$ sed -i 's/"R", /"mamba", "run", "-n", "r_env", "R", /' r_env_kernel/kernel.json
```

:::

Then update the display name used in the Jupyter launcher to match your
environment name.

```bash
$ sed -i 's/"display_name":"R"/"display_name":"R (r_env)"/' r_env_kernel/kernel.json
```

Deactivate your environment.

```bash
$ mamba deactivate
```

Finally, install the kernel into Jupyter and cleanup by deleting the temporary
kernel config directory.

```bash
$ mamba run -n jupyter jupyter kernelspec install r_env_kernel --user
$ rm -rf r_env_kernel
```

When you start up JupyterLab, the new R kernel should be listed in the launcher.

#### Helpful Extensions

##### Rendering

- [GeoJSON Extension](https://github.com/jupyterlab/jupyter-renderers/tree/master/packages/geojson-extension#jupyterlab-geojson){target="\_blank"}

##### Git & GitHub

- [Git Extension](https://github.com/jupyterlab/jupyterlab-git){target="\_blank"}

- [GitHub Extension](https://github.com/jupyterlab/jupyterlab-github#jupyterlab-github){target="\_blank"}

- [Git and Jupyter Notebooks: The Ultimate Guide](https://www.reviewnb.com/git-jupyter-notebook-ultimate-guide){target="\_blank"}

##### Linting, Formatting, and Benchmarking

- [Language Server Protocol Extension](https://github.com/krassowski/jupyterlab-lsp#installation){target="\_blank"}

- [Code Formatter Extension](https://jupyterlab-code-formatter.readthedocs.io/){target="\_blank"}

- [Execution Time Extension](https://github.com/deshaw/jupyterlab-execute-time#jupyterlab-execute-time){target="\_blank"}

- [System Monitor Extension](https://github.com/jtpio/jupyterlab-system-monitor#jupyterlab-system-monitor){target="\_blank"}

##### Spellchecking

- [Spellchecker Extension](https://github.com/jupyterlab-contrib/spellchecker#jupyterlab-spellchecker){target="\_blank"}

##### AI

- [Generative AI Extension](https://github.com/jupyterlab/jupyter-ai){target="\_blank"}

#### Geospatial Libraries

- [ipyleaflet Documentation](https://ipyleaflet.readthedocs.io/en/latest/index.html){target="\_blank"}

### RStudio

While JupyterLab excels at providing an intuitive environment for creating and
editing Python-based computational notebooks, RStudio provides a similarly
intuitive environment for working with the R programming language. It provides
useful tools for writing R scripts, interacting with the R console, or
developing R-based computational notebooks with
[Quarto](https://quarto.org/docs/get-started/hello/rstudio.html){target="\_blank"}
or [RMarkdown](https://rmarkdown.rstudio.com/lesson-2.html){target="\_blank"}.

You can find installers for multiple operating systems
[here](https://posit.co/download/rstudio-desktop/){target="\_blank"}.

When starting a new R project in RStudio, always checkmark 'Use renv with this
project'. This will ensure that you create an isolated and reproducible
environment similar to those that are produced with `mamba`/`conda` or Python's
`venv`.

- [RStudio UserGuide](https://docs.posit.co/ide/user/ide/get-started/){target="\_blank"}

### Visual Studio Code

Visual Studio Code (VS Code) is a more general-purpose programming environment
compared to JupyterLab and RStudio that excels for writing scripts and programs
in Python, JavaScript, Julia, and a broad range of other programming languages.
VS Code is also capable of running computational notebooks through
well-supported extensions, but it can feel less intuitive for some users.

- [UBC Library Research Commons - VS Code Overview in Setting Up a Dev Environment](https://ubc-library-rc.github.io/intro-development-environment/content/02-1.VSCode.html){target="\_blank"}

- [VS Code Documentation](https://code.visualstudio.com/docs){target="\_blank"}

- [Using Git source control in VSCode](https://code.visualstudio.com/docs/sourcecontrol/overview){target="\_blank"}

- _[Visual Studio Code Distilled: Evolved Code Editing for Windows, macOS, and Linux](https://go.exlibris.link/Dt8gkVz2){target="\_blank"}_

#### Helpful Extensions

##### Remote Development

- [Remote Development Extension Overview](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack){target="\_blank"}

##### Jupyter

- [Jupyter Extension Overview](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter){target="\_blank"}

##### Quarto

- [Quarto Extension Overview](https://marketplace.visualstudio.com/items?itemName=quarto.quarto){target="\_blank"}

##### Python

- [Python in VS Code Documentation](https://code.visualstudio.com/docs/languages/python){target="\_blank"}

- [Python Extension Overview](https://marketplace.visualstudio.com/items?itemName=ms-python.python){target="\_blank"}

##### R

- [R in VS Code Documentation](https://code.visualstudio.com/docs/languages/r){target="\_blank"}

- [R Extension Overview](https://marketplace.visualstudio.com/items?itemName=REditorSupport.r){target="\_blank"}
