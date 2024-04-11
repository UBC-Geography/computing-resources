---
output-file: index.html
title: Development Environments
---

## Virtual Environment Managers

Virtual environments are an important tool for isolating multiple Python
projects on a single machine, and their use is highly recommended when starting
new projects. By isolating your projects, you can ensure that each project is
only using the specific Python packages that were identified and installed for
running it. This makes the project easier to reproduce while also reducing
errors caused by clashing package dependencies.

- UBC ARC - Virtual Environment 2023 - Videos:
  [Part 1 (virtualenv)](https://youtu.be/fdMNwQu8MKU?si=Fu_JogcK_SxEsBiC) &
  [Part 2 (conda)](https://youtu.be/BrZ_5rP4b0g?si=GkDWSa9CG5z1uqYx)

- [Getting Started with Conda, Virtual Environments, and Python](https://UBC-Geography.github.io/development-environments/conda-getting-started)

### Conda

Conda is an extremely powerful tool for both managing environments and packages.
Using `conda install` provides the ability to install a range of packages that
either aren't available or can't be installed via Python's built-in package
manager, Pip. Additionally, Conda enables you to install and manage multiple
versions of Python on a single machine using virtual environments.

- [conda User Guide](https://docs.conda.io/projects/conda/en/stable/user-guide/index.html)

If you need to install Conda on your device, we suggest using the link below to
install it using the Miniconda installer.

- [Miniconda, a minimal installer for conda](https://docs.conda.io/en/latest/miniconda.html)

### Python - venv and virtualenv

venv is a lightweight module that has been included with base installations of
Python since version 3.3 and enables you to quickly setup and manage virtual
environments for your project. virtualenv is a more powerful alternative to
venv, but unlike venv it needs to be installed separately via pip. Both modules
lack the same level of functionality as conda, but they can be helpful tools for
those who are still getting comfortable with Python or don't need conda's added
functionalities.

- [venv Documentation](https://docs.python.org/3/library/venv.html)

- [virtualenv Documentation](https://virtualenv.pypa.io/en/latest/)

### R - renv

R's equivalent to virtualenv is renv, which itself is a successor to another
R-based virtual environment manager, packrat. renv has been developed by the
same team behind RStudio and it's usage is recommended within the RStudio user
guide.

- [Introduction to renv](https://rstudio.github.io/renv/articles/renv.html)

- [RStudio User Guide - renv](https://docs.posit.co/ide/user/ide/guide/environments/r/renv.html)

## Integrated Development Environments (IDE)

### Jupyter

Project Jupyter consists of an ecosystem of open-source projects that support
the creation and distribution of computational notebooks. While Jupyter supports
computational notebooks with kernels from a wide range of programming languages,
it specializes in Python while also providing strong support for R and Julia.
Much of the Jupyter ecosystem has been written in and/or runs on Python.

- [Jupyter Tutorial](https://jupyter-tutorial.readthedocs.io/en/latest/index.html)

#### Jupyter Notebooks

The term Jupyter Notebooks is used interchangeably to refer to the Jupyter
Notebook file format and the user interface that has most commonly been to used
to author and edit them. In recent years, the Project Jupyter team has slowly
encouraged users to migrate from the classic Jupyter Notebook interface to
JupyterLab, its more feature-rich successor.

- [Jupyter Notebook (File) Format Documentation](https://nbformat.readthedocs.io/en/latest/index.html)

- [Jupyter Notebook (User Interface) Documentation](https://jupyter-notebook.readthedocs.io/en/latest/index.html)

#### JupyterLab

You can install and run JupyterLab on your local machine in two separate ways.
The traditional and most flexible approach is to install JupyterLab as a Python
package using Pip or Conda and starting it from the Jupyter command line
interface. This approach uses a locally installed version of Python to start a
basic, local server on your machine and then navigates to that server through
your preferred web browser. For those who may be uncomfortable with installing
Python and/or using command line interfaces, Project Jupyter has also released a
simple-to-use desktop application, named JupyterLab Desktop. This application
comes packaged with Python and a default set of packages that are frequently
used in scientific computing.

- [JupyterLab Documentation](https://jupyterlab.readthedocs.io/en/latest/index.html)

- [JupyterLab Desktop - Installation](https://github.com/jupyterlab/jupyterlab-desktop#installation)

- [JupyterLab Desktop User Guide](https://github.com/jupyterlab/jupyterlab-desktop/blob/master/user-guide.md)

#### JupyterHub

The easiest way to get started with creating and editing notebooks is through a
JupyterHub service, like [UBC LT's Open Jupyter](https://open.jupyter.ubc.ca/)
or [UBC Syzygy](https://ubc.syzygy.ca/), which enables you to connect to and
interact with Jupyter servers without having to install anything on your
machine. While convenient, these services come with significant drawbacks in
computing power and will not work well in cases where computations are running
on large datasets.

- [UBC LT - JupyterHub Instructor Guide](https://lthub.ubc.ca/guides/jupyterhub-instructor-guide/)

- [Introduction to Syzygy - Getting Started](https://intro.syzygy.ca/getting-started/)

#### Helpful Extensions

##### Rendering

- [GeoJSON Extension](https://github.com/jupyterlab/jupyter-renderers/tree/master/packages/geojson-extension#jupyterlab-geojson)

##### Git & GitHub

- [Git Extension](https://github.com/jupyterlab/jupyterlab-git)

- [GitHub Extension](https://github.com/jupyterlab/jupyterlab-github#jupyterlab-github)

- [Git and Jupyter Notebooks: The Ultimate Guide](https://www.reviewnb.com/git-jupyter-notebook-ultimate-guide)

##### Linting, Formatting, and Benchmarking

- [Language Server Protocol Extension](https://github.com/krassowski/jupyterlab-lsp#installation)

- [Code Formatter Extension](https://jupyterlab-code-formatter.readthedocs.io/)

- [Execution Time Extension](https://github.com/deshaw/jupyterlab-execute-time#jupyterlab-execute-time)

- [System Monitor Extension](https://github.com/jtpio/jupyterlab-system-monitor#jupyterlab-system-monitor)

##### Spellchecking

- [Spellchecker Extension](https://github.com/jupyterlab-contrib/spellchecker#jupyterlab-spellchecker)

##### AI

- [Generative AI Extension](https://github.com/jupyterlab/jupyter-ai)

#### Geospatial Libraries

- [ipyleaflet Documentation](https://ipyleaflet.readthedocs.io/en/latest/index.html)

### RStudio

While JupyterLab excels at providing an intuitive environment for creating and
editing Python-based computational notebooks, RStudio provides a similarly
intuitive environment for working with the R programming language. It provides
useful tools for writing R scripts, interacting with the R console, or
developing R-based computational notebooks with Quarto or R Markdown.

- [RStudio UserGuide](https://docs.posit.co/ide/user/ide/get-started/)

### Visual Studio Code

Visual Studio Code (VS Code) is a more general-purpose programming environment
compared to JupyterLab and RStudio that excels for writing scripts and programs
in Python, JavaScript, Julia, and a broad range of other programming languages.
VS Code is also capable of running computational notebooks through
well-supported extensions, but it can feel less intuitive for some users.

- [UBC Library Research Commons - VS Code Overview in Setting Up a Dev Environment](https://ubc-library-rc.github.io/intro-development-environment/content/02-1.VSCode.html)

- [VS Code Documentation](https://code.visualstudio.com/docs)

- [Using Git source control in VSCode](https://code.visualstudio.com/docs/sourcecontrol/overview)

- _[Visual Studio Code Distilled: Evolved Code Editing for Windows, macOS, and Linux](https://go.exlibris.link/Dt8gkVz2)_

#### Helpful Extensions

##### Remote Development

- [Remote Development Extension Overview](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack)

##### Jupyter

- [Jupyter Extension Overview](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter)

##### Quarto

- [Quarto Extension Overview](https://marketplace.visualstudio.com/items?itemName=quarto.quarto)

##### Python

- [Python in VS Code Documentation](https://code.visualstudio.com/docs/languages/python)

- [Python Extension Overview](https://marketplace.visualstudio.com/items?itemName=ms-python.python)

##### R

- [R in VS Code Documentation](https://code.visualstudio.com/docs/languages/r)

- [R Extension Overview](https://marketplace.visualstudio.com/items?itemName=REditorSupport.r)
