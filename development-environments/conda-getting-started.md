---
title: Getting Started with Conda, Virtual Environments, and Python
---

There are many different ways to install and start using Python on your personal
device, and no one way is the correct way. How one installs Python often simply
comes down to personal preference. In general, we recommend using a tool called
`mamba`, which has been developed as a faster alternative to the popular package
manager, `conda`, and a lighter alternative to the larger Python distribution
that it's associated with, Anaconda. When performing geospatial computing,
you'll likely be working with multiple projects that depend on not only Python
but other languages too, like R, Julia, or JavaScript. You may also find that
you projects can't always run on the same exact version of Python. `conda` and
`mamba` enable you to easily install and run multiple versions of Python along
with a range of other languages and software packages.

## `conda` and `mamba`

Just as there is with Python, there are multiple ways to install `mamba` and
`conda`. For Windows, we recommend using the latest
[Miniforge3 installer](https://github.com/conda-forge/miniforge?tab=readme-ov-file#miniforge3)
and sticking with the recommended options. Mac OS and Linux users can copy and
run the commands listed
[here](https://github.com/conda-forge/miniforge?tab=readme-ov-file#unix-like-platforms-mac-os--linux)
within their terminal applications.

If you've installed `mamba` on Windows and stuck with the recommended options in
the Miniforge installer, the `mamba` and `conda` commands will only be available
from the Miniforge Prompt application that was included in the installation
process. Use this application rather than Command Prompt or PowerShell. If you
want to pair `mamba` with a more functional shell environment, we've included
instructions for using `mamba` with a Bash shell on Windows in
[UNIX Shells and CLIs](https://ubc-geography.github.io/computing-resources/unix-shells-and-clis/#running-mamba-on-git-bash-for-windows).
For Mac OS and Linux users, the install script adds `mamba` to the PATH variable
thus making it available from a terminal application running a Bash shell.

Once you have `mamba` installed on your machine, follow along with
['Getting Started With Conda'](https://conda.io/projects/conda/en/stable/user-guide/getting-started.html)
to familiarize yourself with some of basic functionalities of `mamba`/`conda`.
As a reminder, Miniforge includes both tools, and they can be used
interchangeably, so use whichever one makes sense to you.

## Virtual Environments

When you install `mamba` with Miniforge, a virtual environment is automatically
created for you, which includes an installation of Python along with `mamba`
itself. This is your base environment, and it can give you quick access to
Python in a pinch, but to ensure the stability of `mamba`, you'll want to avoid
making any changes to this environment apart from running the occasional upgrade
to `mamba`. Before getting started with using `mamba` and Python, it's important
to have an understanding of virtual environments and how `mamba` works with them
to install software and packages onto your machine. If you followed along with
the
[Managing Environments](https://conda.io/projects/conda/en/stable/user-guide/getting-started.html)
section of 'Getting Started With Conda', then you got a very basic introduction
to creating and using virtual environments.

Let's walkthrough the process again by creating a virtual environment that has a
newer version of Python than the one that came pre-installed in the base
environment along with the popular geospatial package, GeoPandas.

To start, you will need to open a terminal on your machine. If you are using
Windows, use the Minforge Prompt as noted before.

Before we can start installing Python and other packages, we will need to create
our new virtual environment. We will name it `py-geo`, which will remind us in
the future that this is a Python environment with geospatial packages.

```bash
$ mamba create --name py-geo
```

Next we'll want to activate our newly created virtual environment, so we can
start interacting with it and installing our packages into it.

```bash
$ mamba activate py-geo
```

When you activate a virtual environment, the name of the environment will be
prepended to your shell prompt, like so:

```bash
(py-geo) $
```

Now that we have our virtual environment activated, we can install the Python
version that we would like to work with alongside GeoPandas.

```bash
(py-geo) $ mamba install python=3.12 geopandas
```

GeoPandas has a decent number of dependencies, many of which other Python
geospatial packages also rely on. You will notice that `mamba` lists those
dependencies and asks if you want to proceed with installing them along with
Python. This is a good time to ensure you did not enter the install command with
a typo and are about to accidentally install the wrong package. If everything
looks correct, respond to the prompt to proceed.

Every package that you install with `mamba` includes information within it that
lists all of its dependent packages and the range of versions that it will be
compatible with. We can use `mamba` to review what dependencies were included
with GeoPandas and Python itself.

```bash
(py-geo) $ mamba list
# packages in environment at ...\miniforge3\envs\py-geo:
#
# Name      Version       Build                 Channel
attrs       23.2.0        pyh71513ae_0          conda-forge
...
python      3.12.4        h889d299_0_cpython    conda-forge
...
zstd        1.5.6         h0ea2cb4_0            conda-forge
```

You will notice that I have abbreviated the list quite a bit with ellipses, but
you can see that we have Python 3.12.4 installed along with GeoPandas' many
dependencies. You may see newer versions listed when you run this command. In a
later step, we will look at how we can upgrade or downgrade Python to another
version within this environment.

To ensure your virtual environment is reproducible for both yourself and
collaborators, it's important to keep an up-to-date file that lists the packages
you used while running your code and store it alongside your code in a version
control system, like Git. `mamba` includes the ability to generate this file for
you by taking a snapshot of all the packages installed within an environment and
store the name and versions of those packages into a text-based YAML (.yml) file
using the following command.

```bash
(py-geo) $ mamba env export --no-builds > environment.yml
```

To test our file, let's make one more environment using the environment file
that we just generated to see how it works, and we will just list our
environments again to verify that it was created.

```bash
(py-geo) $ mamba deactivate
$ mamba env create -n testenv -f environment.yml
$ mamba info --envs
# virtual environments:
#
base                   * C:\Users\<username>\miniforge3
py-geo                   C:\Users\<username>\miniforge3\envs\py-geo
testenv                  C:\Users\<username>\miniforge3\envs\testenv
```

Next let us just do a little cleanup by removing the `testenv` environment that
we just created and verify that it is no longer on our machine.

```bash
$ mamba remove -n testenv --all
$ mamba info --envs
# virtual environments:
#
base                   * C:\Users\<username>\miniforge3
py-geo                   C:\Users\<username>\miniforge3\envs\py-geo
```

## Python

Now I want to return to my `py-geo` environment, and rather than running Python
3.12.4, I want to downgrade my Python version to be one minor release older. We
can use the following commands to activate the `py-geo` environment and then use
the search tool to see what Python versions are available. One important thing
to note is that `conda` and `mamba` can pull packages from different channels,
which are managed by different groups and organizations. By default, `mamba`
pulls from the `conda-forge` channel, which includes the most expansive and
up-to-date set of packages. It's often recommended that you start with the
`conda-forge` channel and stick to it. Using multiple channels in a single
environment can cause a range of conflicts that may break your environment.

```bash
$ mamba activate py-geo
(py-geo) $ mamba search python
Loading channels: done
#Name               Version         Build                  Channel
python              2.7.12          0                      conda-forge
...
python              3.12.4          h889d299_0_cpython     conda-forge
```

You will notice that I have abbreviated the list quite a bit with an ellipsis,
but I currently have access to a range of Python versions from 2.7.12 to 3.12.4.

Now which Python version you install will heavily depend on the other packages
and software that you intend to use within your environment. You will need to
take a close look at what Python versions the packages that you want to use are
compatible with.

It's usually a good choice to select one minor version older than the newest
version of Python. This ensures a broader level of compatibility with a range of
packages. For many package maintainers, it can be quite a bit of work to update
their code to make it compatible with the latest minor release of Python, so we
can account for this by using an earlier minor release.

To downgrade my version of Python from 3.12.4 to 3.11.x, I can run the following
command.

```bash
(py-geo) $ mamba install python=3.11
```

Every October, Python releases a new minor version. In a variety of cases, it
can be useful to upgrade to the next minor release either to access a new
feature or to just keep your environment up-to-date. To update a package with
`mamba` alongside all of its dependencies and the packages that depend on it,
you can use the following command:

```bash
(py-geo) $ mamba update python
```

And voilà, I'm back to Python 3.12.4 and ready to go. A newer version of Python
may have been released since writing this, so you might actually see a newer
version installed in your environment. And remember to test your code after each
package upgrade to ensure that it's still running as expected.
