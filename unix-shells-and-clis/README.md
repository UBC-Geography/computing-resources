---
output-file: index.html
title: Unix Shells & Command Line Interfaces (CLI)
---

Having confidence when using a Unix shell, particularly Bash, is crucial when
working within an HPC environment. It can also be extraordinarily helpful when
setting up development environments, running scripts in Python or R, or using
containers and command line tools.

If you are looking to install Bash, you can find a helpful walkthrough
[here](https://ubc-library-rc.github.io/intro-git/#pre-workshop-setup).

UBC Library Research Commons frequently runs introductory workshops on Bash,
which are listed [here](https://libcal.library.ubc.ca/calendar/?t=g&q=unix). And
the materials for these workshops are available below:

- [Introduction to the UNIX Shell](https://ubc-library-rc.github.io/intro-shell/)

- [Intermediate UNIX Shell](https://ubc-library-rc.github.io/advanced-shell/)

Additionally, the SFU's Research Computing Group provides a full-day workshop on
Bash during their annual Summer School in early June with some of the materials
for that course available below:

- [Bash Course and Webinar](https://mint.westdri.ca/bash/)

Additional resources:

- [Software Carpentry - The UNIX Shell](https://swcarpentry.github.io/shell-novice/)

- [Intro to Linux and the Bash Shell in HPC Environments](https://confluence.it.ubc.ca/display/UARC/Introduction+to+Linux+and+Using+the+Command+Line+Interface)

- [UBC ARC - Intro to the Unix Shell - Video](https://youtu.be/gKz0-y4DXws?si=1zw4pO6GeOosxzfK)

- [Intro to Linux Shell -- Video Lecture](https://www.youtube.com/watch?v=eLF598YqbFw)

- _Pro Bash_ : [UBC Library](https://go.exlibris.link/6FxkGXft) |
  [WorldCat](https://search.worldcat.org/title/1409222493)

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

- [GDAL Documentation](https://gdal.org/programs/index.html#general)

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
[here](https://imagemagick.org/script/download.php#windows), which will enable
you to use ImageMagick from your preferred shell. Mac OS and Linux users can
install ImageMagick from the conda-forge repository using `conda` or `mamba`
with one of the following commands:

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

- [ImageMagick Documentation](https://imagemagick.org/script/command-line-tools.php)

- [Command-line image processing with ImageMagick](https://training.westdri.ca/tools/visualization/#imagemagick)

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

- [FFmpeg Documentation](https://ffmpeg.org/ffmpeg.html)

- _Quick Start Guide to FFmpeg_ [UBC Library](https://go.exlibris.link/XSRj7ZcH)
  | [WorldCat](https://search.worldcat.org/title/1369033645)
