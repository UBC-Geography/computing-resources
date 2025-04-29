---
output-file: index.html
title: Unix Shells & Command Line Interfaces (CLI)
# change to date to last-modified after next modification
date: 2025-01-16
---

Having confidence when using a Unix shell, particularly Bash, is crucial when
working within an HPC environment. It can also be extraordinarily helpful when
setting up development environments, running scripts in Python or R, or using
containers and command line tools.

Via their
[Opensource Computing for Earth Science Education (OCESE) Project](https://eoas-ubc.github.io/index.html){target="\_blank"},
UBC's Department of Earth, Ocean and Atmospheric Science has compiled an
excellent and concise tutorial for both Bash and its Windows equivalent,
Powershell, on the
[Command Line & Shells page](https://eoas-ubc.github.io/tut-commandline.html){target="\_blank"}.

If you are a Windows user looking to install Bash, you can find a helpful
walkthrough
[here](https://ubc-library-rc.github.io/intro-git/#pre-workshop-setup){target="\_blank"}.

UBC Library Research Commons frequently runs introductory workshops on Bash,
which are listed
[here](https://libcal.library.ubc.ca/calendar/?t=g&q=unix){target="\_blank"}.
And the materials for these workshops are available below:

- [Introduction to the UNIX Shell](https://ubc-library-rc.github.io/intro-shell/){target="\_blank"}

- [Intermediate UNIX Shell](https://ubc-library-rc.github.io/advanced-shell/){target="\_blank"}

Additionally, the SFU's Research Computing Group provides a full-day workshop on
Bash during their annual Summer School in early June with some of the materials
for that course available below:

- [Bash Course and Webinar](https://mint.westdri.ca/bash/){target="\_blank"}

Additional resources:

- [Software Carpentry - The UNIX Shell](https://swcarpentry.github.io/shell-novice/){target="\_blank"}

- [Intro to Linux and the Bash Shell in HPC Environments](https://confluence.it.ubc.ca/display/UARC/Introduction+to+Linux+and+Using+the+Command+Line+Interface){target="\_blank"}

- [UBC ARC - Intro to the Unix Shell - Video](https://youtu.be/gKz0-y4DXws?si=1zw4pO6GeOosxzfK){target="\_blank"}

- [Intro to Linux Shell -- Video Lecture](https://www.youtube.com/watch?v=eLF598YqbFw){target="\_blank"}

- _Pro Bash_ :
  [UBC Library](https://go.exlibris.link/6FxkGXft){target="\_blank"} |
  [WorldCat](https://search.worldcat.org/title/1409222493){target="\_blank"}

## Running mamba on Git-Bash for Windows

When installing mamba via Miniforge with the recommended options, it is not
included in your PATH by default, so you'll only be able use it by running
Miniforge Prompt from your Start Menu. For most folks that might be just fine,
but we recommend adding both the `mamba` and `conda` commands to your Git-Bash
environment, so you can more easily take advantage of Bash and Git.

Start by locating the 'profile.d' folder that was installed with Miniforge via
the File Explorer. Most likely this would located at:
`C:\Users\<your_username>\miniforge3\etc`. Right click the 'profile.d' folder
and select 'Open Git Bash here'. In the Git Bash terminal, run the following
commands:

```bash
$ echo "source '${PWD}/conda.sh'" >> ~/.bashrc
$ echo "source '${PWD}/mamba.sh'" >> ~/.bashrc
```

Then restart your Bash session and check that mamba works:

```bash
$ source ~/.bashrc
$ mamba --version
```

You should see output telling you the versions of mamba and conda that are
installed.

## Command Line Tools

### GDAL

GDAL is used by a variety of GIS software to read and write geospatial data, and
it is one of the most commonly used geospatial libraries. A range of
functionalities can be accessed through the various CLI tools that accompany it,
including conversions between a large collection of raster and vector data
formats.

- [GDAL Documentation](https://gdal.org/programs/index.html#general){target="\_blank"}

You can install GDAL from the conda-forge repository using `conda` or `mamba`
with one of the following commands:

::: {.panel-tabset}

## Mamba

```bash
$ mamba install libgdal -y
```

## Conda

```bash
$ conda install -c conda-forge libgdal -y
```

:::

### ImageMagick

When processing large collections of images, ImageMagick is a very popular tool
with an extraordinary amount of functionality. It's commonly used to convert,
resize, and optimize images files in various formats.

If you are using Windows, you can find an installer
[here](https://imagemagick.org/script/download.php#windows){target="\_blank"},
which will enable you to use ImageMagick from your preferred shell. Mac OS and
Linux users can install ImageMagick from the conda-forge repository using
`conda` or `mamba` with one of the following commands:

::: {.panel-tabset}

## Mamba

```bash
$ mamba install imagemagick -y
```

## Conda

```bash
$ conda install -c conda-forge imagemagick -y
```

:::

- [ImageMagick Documentation](https://imagemagick.org/script/command-line-tools.php){target="\_blank"}

- [Command-line image processing with ImageMagick](https://training.westdri.ca/tools/visualization/#imagemagick){target="\_blank"}

### FFmpeg

FFmpeg is an extremely powerful tool for batch processing both video and audio
files. It can be installed using one of the following commands:

::: {.panel-tabset}

## Mamba

```bash
$ mamba install ffmpeg -y
```

## Conda

```bash
$ conda install -c conda-forge ffmpeg -y
```

:::

- [FFmpeg Documentation](https://ffmpeg.org/ffmpeg.html){target="\_blank"}

- _Quick Start Guide to FFmpeg_
  [UBC Library](https://go.exlibris.link/XSRj7ZcH){target="\_blank"} |
  [WorldCat](https://search.worldcat.org/title/1369033645){target="\_blank"}
