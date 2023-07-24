# Geography Computing Resources & Documentation

This repository includes a listing of computing resources and accompanying documentation that can be helpful in familiarizing
oneself with various tools and software that are used in Geography research, instruction, and learning. For more related materials and
workshop opportunities, check out [UBC Library Research Commons Workshops](https://researchcommons.library.ubc.ca/workshops/).

If you have recommendations for materials to add to this list, feel free to create a pull request or reach out to kellen.malek@ubc.ca.

## WordPress

Open-source content management system software that is used to host a
wide range of websites and web applications. Both UBC Blogs and UBC CMS
are built on top of this software, so UBC provides a large collection of
documentation to help faculty and students in getting started with using
it. The wide adoption of this software also means there is plenty of
documentation for self-hosting a WordPress server, but strong caution
should be taken as security vulnerabilities are frequently identified
and taken advantage of by bad actors.

- [Arts ISIT Video Tutorials](https://isit.web.arts.ubc.ca/video-tutorial-introduction-to-ubc-cms/)

- [IThemes Tutorials](https://ithemes.com/tutorials/)

- [Arts ISIT WordPress Resources](https://isit.arts.ubc.ca/resources/)

- [WordPress Clinics at CTLT](https://events.ctlt.ubc.ca/?s=wordpress)

### UBC Blogs

- [UBC Blogs vs. UBC CMS](https://support.cms.ubc.ca/cms-manual/getting-started/differences-between-ubc-cms-and-ubc-blogs/)

- [UBC Blogs FAQ](https://blogs.ubc.ca/faq/)

- [UBC Blogs Video Tutorials](https://wiki.ubc.ca/UBC_Blogs_Screencasts)

- [UBC Blogs Instructor Guide](https://lthub.ubc.ca/guides/ubc-blogs-instructor-guide/)

### UBC CMS

- [UBC CMS Manual](https://support.cms.ubc.ca/cms-manual/)

### Cloud Hosting

- [UBC IT Shared Hosting](https://it.ubc.ca/services/web-servers-storage/shared-web-hosting)

- [WordPress Documentation](https://wordpress.org/documentation/)

- [WordPress 101 -- Video Course](https://learning.oreilly.com/videos/wordpress-101/9781800566415/?sso_link=yes&sso_link_from=univ-british-columbia)

- [WordPress: The Missing Manual](http://resolve.library.ubc.ca/cgi-bin/catsearch?bid=11890511)

## Static Site Generators (SSG) / Web Publishing

As alternatives to WordPress, static site generators give up easy-to-use
interfaces via a content management system and a range of other
functionalities to create faster, more reliable, and more secure
websites, where content is managed via a set of Markdown files.
Additionally, these tools often have smaller sets of themes that users
can install to customize the styling of their website, thus requiring a
better understanding of HTML, CSS, and JavaScript to develop a more
customized look and feel to a website.

### Quarto

Developed by the same company working on RStudio, Quarto provides a
powerful tool for publishing scientific and technical work in a range of
formats and acts as a successor to R Markdown. Code in Python, R, Julia,
and JavaScript can all be represented and rendered along with
Pandoc-style Markdown. Interactive visualizations can also be embedded
on supported formats using R Shiny, Observable JS, or Jupyter Widgets.
Note: If rendering and exporting HTML files in RStudio using Quarto,
ensure you also export the quarto_files directory, which holds necessary
CSS and JavaScript files.

- [Quarto Webinars](https://mint.westdri.ca/tools/quarto_webinar.html)

- [Quarto Documentation](https://quarto.org/docs/guide/)

### R Markdown (R)

Developed by the company behind RStudio, R Markdown provides an
authoring framework that enables code to be rendered alongside Markdown
and published in multiple formats. See Quarto for a successor to R
Markdown. Note: HTML files rendered via R Markdown use inline scripts
and CSS, which can create sometimes unnecessarily large files, but they
ensure that the file displays consistently without external files.

- [R Markdown Documentation](https://rmarkdown.rstudio.com/lesson-1.html)

### Jekyll (Ruby)

One of the most used static site generators. This SSG integrates
smoothly with GitHub Pages to quickly render websites directly from a
GitHub repository. Due to its wide adoption, it also includes a wide
range of open-source themes that can be used to customize the style of a
website.

- [Introduction to Jekyll](https://ubc-library-rc.github.io/intro-jekyll)

- [Intermediate Jekyll](https://ubc-library-rc.github.io/intermediate-Jekyll/)

- [Building a project website with Jekyll and GitHub Pages](https://ubc-library-rc.github.io/intro-project-sites/)

- [Jekyll Documentation](https://jekyllrb.com/docs/)

## Digital Exhibit Tools

Storing and presenting digital assets, like images, audio, and video
files, can be easily managed via content management systems and static
site generators that specialize in digital exhibits.

- [Survey of Digital Exhibit Tools](https://ubc-library-rc.github.io/digital-exhibits-survey/)

### Omeka Classic & Omeka-S

Omeka Classic is targeted towards small, individually developed
projects, while Omeka-S focuses on developing larger scale,
institutional-wide repositories with multiple collections or projects.
Both are considered web applications as they include content management
systems that provide an easy-to-use interface for developing and
managing digital exhibits.

- [Building Digital Exhibits with Omeka](https://github.com/ubc-library-rc/intro-omeka)

- [Omeka: A User's Guide: Introduction](https://guides.library.illinois.edu/omeka/intro)

#### Cloud Hosting

- [UBC IT Shared Hosting](https://it.ubc.ca/services/web-servers-storage/shared-web-hosting)

- [Omeka Classic Documentation](https://omeka.org/classic/docs/)

- [Omeka-S Documentation](https://omeka.org/s/docs/user-manual/)

### CollectionBuilder

Lacking a content management system, CollectionBuilder centers the
development and management of digital exhibits around CSVs and Markdown.
Built as a theme around a static site generator (Jekyll),
CollectionBuilder creates digital exhibits as fast and easy-to-preserve
websites.

- [CollectionBuilder Documentation](https://collectionbuilder.github.io/cb-docs/)

## Research Data Management (RDM)

- [Research Data Management -- File Naming](https://ubc-library-rc.github.io/rdm/content/01_file_naming.html)

- [Research Data Management -- File Formats](https://ubc-library-rc.github.io/rdm/content/02_file_formats.html)

- [Research Data Management Video -- Part 1](https://www.youtube.com/watch?v=TxYlHMieXAM)

- [Research Data Management Video -- Part 2](https://www.youtube.com/watch?v=q5eXXps1o04)

### GIS-Related Standards

- [Open Geospatial Consortium Standards](https://www.ogc.org/standard/sfs/)

## Python

Python is one of the most popular programming languages in the world. Its low learning curve paired with a massive ecosystem has made it a powerful tool for geospatial computing. GIS software like QGIS and ArcGIS, provide the ability to extend their functionality through Python, while many programming libraries that have been created to efficiently perform geospatial computing tasks have been either written in Python, released as Python packages, and/or include application programming interfaces (APIs) that coherently communicate with Python code.

- _[Python for Geographic Data Analysis](https://pythongis.org/)_

- _[Python Crash Course](http://resolve.library.ubc.ca/cgi-bin/catsearch?bid=12472396)_

### Geospatial Books

- _[Geographic Data Science with Python](https://geographicdata.science/book/intro.html)_

- _[Learning Geospatial Analysis with Python: Understand GIS Fundamentals and Perform Remote Sensing Data Analysis Using Python 3. 7](http://resolve.library.ubc.ca/cgi-bin/catsearch?bid=11126768)_

- _[GIS Algorithms](http://resolve.library.ubc.ca/cgi-bin/catsearch?bid=10279472)_

- _[Python for Geospatial Data Analysis](http://resolve.library.ubc.ca/cgi-bin/catsearch?bid=12429886)_

- _[Applied Geospatial Data Science with Python](http://resolve.library.ubc.ca/cgi-bin/catsearch?bid=12613206)_

- _[Mastering Geospatial Analysis with Python: Explore GIS Processing and Learn to Work with GeoDjango, CARTOframes and MapboxGL-Jupyter](http://resolve.library.ubc.ca/cgi-bin/catsearch?bid=10274346)_

- _[Machine Learning on Geographical Data Using Python Introduction into Geodata with Applications and Use Cases](http://resolve.library.ubc.ca/cgi-bin/catsearch?bid=12453975)_

#### Extending GIS Software

- _[A Geographer's Guide to Computing Fundamentals: Python in ArcGIS Pro](http://resolve.library.ubc.ca/cgi-bin/catsearch?bid=12441298)_

- _[Python for ArcGIS Pro](http://resolve.library.ubc.ca/cgi-bin/catsearch?bid=12191128)_

- _[Advanced Python scripting for ArcGIS Pro](http://resolve.library.ubc.ca/cgi-bin/catsearch?bid=11878622)_

- _[Mastering Geospatial Development with QGIS 3](http://resolve.library.ubc.ca/cgi-bin/catsearch?bid=10274348)_

- _[QGIS Python programming cookbook](http://resolve.library.ubc.ca/cgi-bin/catsearch?bid=10262853)_

### Geospatial Libraries/Packages

- [Awesome Geospatial - Python](https://github.com/sacridini/Awesome-Geospatial#python)

- [GDAL Python Documentation](https://gdal.org/api/python_bindings.html)

### Virtual Environment Managers

Virtual environments are an important tool for isolating multiple Python projects on a single machine, and their use is highly recommended when starting new projects. By isolating your projects, you can ensure that each project is only using the specific Python packages that were identified and installed for running it. This makes the project easier to reproduce while also reducing errors caused by clashing package dependencies.

#### Conda

Conda is an extremely powerful tool for both managing environments and packages. Using `conda install`
provides the ability to install a range of powerful packages that aren't available via Python's built-in package manager, pip. Additionally, Conda enables you to install and manage multiple versions of Python on a single machine using virtual environments.

If you need to install Conda on your device, we suggest using the link below to install it using the Miniconda installer.

- [Miniconda, a minimal installer for conda](https://docs.conda.io/en/latest/miniconda.html)

- [conda User Guide](https://docs.conda.io/projects/conda/en/stable/user-guide/index.html)

#### venv and virtualenv

venv is a lightweight module that has been included with base installations of Python
since version 3.3 and enables you to quickly setup and manage virtual environments for your project.
virtualenv is a more powerful alternative to venv, but unlike venv it needs to be installed
separately via pip. Both modules lack the same level of functionality as conda, but they can be helpful tools for those
who are still getting comfortable with Python or don't need conda's added functionalities.

- [venv Documentation](https://docs.python.org/3/library/venv.html)

- [virtualenv Documentation](https://virtualenv.pypa.io/en/latest/)

### Linting

Using a static analysis tool, or linter, is a common best practice among
programmers that helps in identifying and fixings mistakes when writing code by
ensuring that you follow the correct syntax and a guiding set of best
practices.

- [flake8 Documentation](https://flake8.pycqa.org/en/latest/)

### Type Checking

While Python is inherently a dynamically typed language, meaning you the
programmer don't have to worry about the data types of each variable,
static types can be helpful for reducing bugs when writing complex
scripts or programs. Mypy enables programmers to annotate types into
their code and returns a helpful error when those types aren't
explicitly followed.

- [mypy Documentation](https://mypy.readthedocs.io/en/stable/)

### Formatting

Sometimes writing code can get a bit messy. Formatters, like black, can
automatically reformat your code to make it cleaner and easier to read
while following a set of standards and best practices.

- [black Documentation](https://black.readthedocs.io/en/stable/)

### Testing Framework

Similar to type checking, unit testing can be a helpful tool when
writing large and complex scripts or programs. Testing frameworks, like
pytest, which is included in Python's standard library, enable you to
define tests that can run over your functions and ensure they are
following expected behavior in a range of practical scenarios.

- [pytest Documentation](https://docs.pytest.org/en/7.3.x/)

### Other Related Libraries/Packages

- [SciPy Documentation](https://docs.scipy.org/doc/scipy/)

- [NumPy Documentation](https://numpy.org/doc/stable/)

- [pandas Documentation](https://pandas.pydata.org/docs/)

- [scikit-learn Documentation](https://scikit-learn.org/stable/user_guide.html)

- [matplotlib User Guide](https://matplotlib.org/stable/users/index)

- [seaborn Tutorial](https://seaborn.pydata.org/tutorial.html)

- [bokeh Documentation](https://docs.bokeh.org/en/latest/docs/user_guide.html)

- [plotly Fundamentals](https://plotly.com/python/plotly-fundamentals/)

- [Folium Documentation](https://python-visualization.github.io/folium/)

- [Dask Documentation](https://docs.dask.org/en/stable/)

## R

- [Introduction to R for Spatial Data Science](https://rspatial.org/intr/index.html)

- [Spatial Data Science with Applications in R](https://r-spatial.org/book/)

### Geospatial Libraries/Packages

- [CRAN Task View: Analysis of Spatial Data](https://cran.r-project.org/web/views/Spatial.html)

- [Awesome Geospatial - R](https://github.com/sacridini/Awesome-Geospatial#r)

### Virtual Environment Managers

- Conda

- renv

### Linting

Using a static analysis tool, or linter, is a common best practice among
programmers that helps identify mistakes when writing code by ensuring
that you follow the correct syntax and a guiding set of best practices.

- [lintr Documentation](https://lintr.r-lib.org/)

### Formatting

Sometimes writing code can get a bit messy. Formatters, like styler, can
automatically reformat your code to make it cleaner and easier to read
while following a set of standards and best practices.

Note: RStudio includes a formatting tool via Code \> Reformat Code

- [styler Documentation](https://styler.r-lib.org/)

### Benchmarking

When writing code, there is often a wide array of ways in which a task
can be completed. Benchmarking your functions can help you find the most
efficient approach possible. This is particularly important when writing
scripts and programs that will be used on large datasets and/or on high
performance computers.

- [bench Documentation](https://cran.r-project.org/web/packages/bench/bench.pdf)

### Other Related Libraries/Packages

- [trajectories: Classes and Methods for Trajectory Data](https://cran.r-project.org/web/packages/trajectories/vignettes/article.pdf)

- [trajectories Reference Manual](https://cran.r-project.org/web/packages/trajectories/trajectories.pdf)

- [xts: Extensible Time Series](https://cran.r-project.org/web/packages/xts/vignettes/xts.pdf)

- [xts Reference Manual](https://cran.r-project.org/web/packages/xts/xts.pdf)

- [zoo: An S3 Class and Methods for Indexed Totally Ordered Observations](https://cran.r-project.org/web/packages/zoo/vignettes/zoo.pdf)

- [zoo Reference Manual](https://cran.r-project.org/web/packages/zoo/zoo.pdf)

- [tidygraph Reference Manual](https://cran.r-project.org/web/packages/tidygraph/tidygraph.pdf)

- [proj4 Reference Manual](https://cran.r-project.org/web/packages/proj4/proj4.pdf)

- [Introduction to dplyr](https://cran.r-project.org/web/packages/dplyr/vignettes/dplyr.html)

- [dpylr Documentation](https://dplyr.tidyverse.org/)

- [dpylr Reference Manual](https://cran.r-project.org/web/packages/dplyr/dplyr.pdf)

- [tidyr Documentation](https://tidyr.tidyverse.org/)

- [tidyr Reference Manual](https://cran.r-project.org/web/packages/tidyr/tidyr.pdf)

- [Introduction to CAST](https://hannameyer.github.io/CAST/articles/cast01-CAST-intro.html)

- [CAST Reference Manual](https://cran.r-project.org/web/packages/CAST/CAST.pdf)

- [Spatial Data in the mlr3 Ecosystem](https://mlr-org.com/gallery/technical/2023-02-27-land-cover-classification/)

- [mlr3Spatial Reference Manual](https://cran.r-project.org/web/packages/mlr3spatial/mlr3spatial.pdf)

- [performanceEstimation GitHub README](https://github.com/ltorgo/performanceEstimation/blob/master/README.md)

- [performanceEstimation Reference Manual](https://cran.r-project.org/web/packages/performanceEstimation/performanceEstimation.pdf)

- [Interactive web-based data visualization with R, plotly, and shiny](https://plotly-r.com/)

- [plotly Reference Manual](https://plotly-r.com/)

## JavaScript

### GIS Libraries/Packages

#### Web Mapping

- [Awesome Geospatial -- Web Mapping](https://github.com/sacridini/Awesome-Geospatial#web-map-development)

##### Leaflet

- [Web mapping with LeafletJS](https://ubc-library-rc.github.io/gis-intro-leaflet/)

- [Leaflet Tutorials](https://leafletjs.com/examples.html)

##### Mapbox

- [Mapbox GL JS Guide](https://docs.mapbox.com/mapbox-gl-js/guides/)

#### Visualizations

- [D3 Documentation](https://github.com/d3/d3/wiki)

- [Observable Plot Documentation](https://observablehq.com/plot/getting-started)

#### Observable JS

- [Observable Documentation](https://observablehq.com/@observablehq/documentation?collection=@observablehq/documentation)

## Jupyter

Project Jupyter consists of an ecosystem of open-source projects that support the creation and distribution of computational notebooks. While Jupyter supports computational notebooks with kernels from a wide range of programming languages, it specializes in Python followed by R and Julia. Much of the Python ecosystem has been written in and/or runs on Python.

### Jupyter Notebooks

The term Jupyter Notebooks is used interchangeably to refer to the Jupyter Notebook file format and the application used to author and edit them, the Jupyter Notebook user interface. In recent years, the Project Jupyter team has slowly encouraged users to migrate from the classic Jupyter Notebook interface to JupyterLab, its more feature-rich successor.

- [Jupyter Notebook (File) Format Documentation](https://nbformat.readthedocs.io/en/latest/index.html)

- [Jupyter Notebook (User Interface) Documentation](https://jupyter-notebook.readthedocs.io/en/latest/index.html)

### JupyterLab

JupyterLab can be installed and ran on your local machine in two separate ways. The traditional and most flexible approach is to install JupyterLab as a Python package using Pip or Conda and starting it with a single command via the Jupyter command line interface. This approach uses a locally installed version of Python to start a basic server on your machine and then navigates to that server through your preferred web browser. For those who may be uncomfortable with installing Python and/or using command line interfaces, Project Jupyter has also released a simple-to-use desktop application, named JupyterLab Desktop. This application comes packaged with Python and a default set of packages that are frequently used in scientific computing.

- [JupyterLab Documentation](https://jupyterlab.readthedocs.io/en/latest/index.html)

- [JupyterLab Desktop - Installation](https://github.com/jupyterlab/jupyterlab-desktop#installation)

- [JupyterLab Desktop User Guide](https://github.com/jupyterlab/jupyterlab-desktop/blob/master/user-guide.md)

### JupyterHub

The easiest way to get started with creating and editing notebooks is through a JupyterHub service, like [UBC LT's Open Jupyter]() or [UBC Syzygy](). While convenient, these services come with significant drawbacks in computing power and will not work well in cases where computations are running on large datasets.

- [UBC LT - JupyterHub Instructor Guide](https://lthub.ubc.ca/guides/jupyterhub-instructor-guide/)

- [Introduction to Syzygy - Getting Started](https://intro.syzygy.ca/getting-started/)

### Helpful Extensions

#### Rendering

- [GeoJSON Extension](https://github.com/jupyterlab/jupyter-renderers/tree/master/packages/geojson-extension#jupyterlab-geojson)

#### Git & GitHub

- [Git Extension](https://github.com/jupyterlab/jupyterlab-git)

- [GitHub Extension](https://github.com/jupyterlab/jupyterlab-github#jupyterlab-github)

- [Git and Jupyter Notebooks: The Ultimate Guide](https://www.reviewnb.com/git-jupyter-notebook-ultimate-guide)

#### Linting, Formatting, and Benchmarking

- [Language Server Protocol Extension](https://github.com/krassowski/jupyterlab-lsp#installation)

- [Code Formatter Extension](https://jupyterlab-code-formatter.readthedocs.io/)

- [Execution Time Extension](https://github.com/deshaw/jupyterlab-execute-time#jupyterlab-execute-time)

- [System Monitor Extension](https://github.com/jtpio/jupyterlab-system-monitor#jupyterlab-system-monitor)

#### Spellchecking

- [Spellchecker Extension](https://github.com/jupyterlab-contrib/spellchecker#jupyterlab-spellchecker)

#### AI

- [Generative AI Extension](https://github.com/jupyterlab/jupyter-ai)

### Geospatial Libraries

- [ipyleaflet Documentation](https://ipyleaflet.readthedocs.io/en/latest/index.html)

## RStudio

- [RStudio UserGuide](https://docs.posit.co/ide/user/ide/get-started/)

## Visual Studio Code

- [VS Code Overview in Setting Up a Dev Environment](https://ubc-library-rc.github.io/intro-development-environment/content/02-1.VSCode.html)

- [VS Code Documentation](https://code.visualstudio.com/docs)

- [Using Git source control in VSCode](https://code.visualstudio.com/docs/sourcecontrol/overview)

### Helpful Extensions

#### Remote Development

- [Remote Development Extension Overview](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack)

#### Jupyter Notebooks

- [Jupyter Extension Overview](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter)

#### Quarto

- [Quarto Extension Overview](https://marketplace.visualstudio.com/items?itemName=quarto.quarto)

#### Python

- [Python in VS Code Documentation](https://code.visualstudio.com/docs/languages/python)

- [Python Extension Overview](https://marketplace.visualstudio.com/items?itemName=ms-python.python)

#### R

- [R in VS Code Documentation](https://code.visualstudio.com/docs/languages/r)

- [R Extension Overview](https://marketplace.visualstudio.com/items?itemName=REditorSupport.r)

## Git & GitHub

- [Introduction to Git and GitHub](https://ubc-library-rc.github.io/intro-git/)

- [Git Tutorial and Workshops](https://mint.westdri.ca/git/)

- [GitHub Desktop Documentation](https://docs.github.com/en/desktop/installing-and-configuring-github-desktop/overview/getting-started-with-github-desktop)

- [GitHub Documentation](https://docs.github.com/en)

- [GitHub InstructorGuide](https://lthub.ubc.ca/guides/github-instructor-guide/)

- [Building a project website with Jekyll and GitHub Pages](https://ubc-library-rc.github.io/intro-project-sites/)

## SQL Databases

- [How to create and access MySQL and PostgreSQL databases on DRI systems - Video](https://youtu.be/3uHSXXQwJpQ)

### PostgreSQL

#### Hosting

##### Alliance

- [Database Servers -- Cedar PostreSQL](https://docs.alliancecan.ca/wiki/Database_servers#Cedar_PostgreSQL_server)

##### Cloud / SaaS Providers

- [MicrosoftAzure](https://azure.microsoft.com/en-ca/products/postgresql/)

- [AWS](https://aws.amazon.com/rds/postgresql/)

- [Google Cloud](https://cloud.google.com/sql/docs/postgres)

- [Supabase](https://supabase.com/docs/guides/database)

- [Railway](https://docs.railway.app/databases/postgresql)

#### GIS Extensions / Libraries

- [PostGIS](https://postgis.net/documentation/)

- [pgRouting](https://docs.pgrouting.org/latest/en/pgRouting-introduction.html)

### MySQL

#### Hosting

##### Alliance

- [Database Servers -- Cedar MySQL](https://docs.alliancecan.ca/wiki/Database_servers#Cedar_MySQL_server)

##### Cloud / SaaS Providers

- [Microsoft Azure](https://azure.microsoft.com/en-ca/products/mysql/)

- [AWS](https://aws.amazon.com/rds/mysql/)

- [Google Cloud](https://cloud.google.com/sql/docs/mysql)

- [PlanetScale](https://planetscale.com/docs)

- [Railway](https://docs.railway.app/databases/mysql)

#### GIS Extensions / Libraries

- [MySQL Spatial](https://dev.mysql.com/doc/refman/8.0/en/spatial-analysis-functions.html)

## Unix Shells & Command Line Interfaces (CLI)

- [Introduction to the UNIX Shell](https://ubc-library-rc.github.io/intro-shell/)

- [Intermediate UNIX Shell](https://ubc-library-rc.github.io/advanced-shell/)

- [Bash Course and Webinar](https://mint.westdri.ca/bash/)

- [Intro to Linux and the Bash Shell in HPC Environments](https://confluence.it.ubc.ca/display/UARC/Introduction+to+Linux+and+Using+the+Command+Line+Interface)

- [Intro to Linux Shell -- Video Lecture](https://www.youtube.com/watch?v=eLF598YqbFw)

## High Performance Computing (HPC)

- [Introduction to Compute Canada (Alliance) Video](https://www.youtube.com/watch?v=hWkWAaNBILs)

- [Intro to Linux and the Bash Shell in HPC Environments](https://confluence.it.ubc.ca/display/UARC/Introduction+to+Linux+and+Using+the+Command+Line+Interface)

- [Research Computing Bootcamp Videos](https://www.ualberta.ca/information-services-and-technology/research-computing/bootcamps.html?1=HPC)

- [Geospatial Analysis with HPC Video](https://youtu.be/wRmRnVMjKXM)

### QGIS in HPC

- [Alliance Documentation](https://docs.alliancecan.ca/wiki/QGIS)

### Jupyter in HPC

- [Alliance Documentation](https://docs.alliancecan.ca/wiki/JupyterHub)

### Python in HPC

- [Working with the Python Dask (Parallelization) Library Video](https://youtu.be/uGy5gT2vLdI)

### R in HPC

- [Introduction to HPC in R Webinar](https://mint.westdri.ca/r/intro_hpc.html)

- [High-performance R Tutorial](https://mint.westdri.ca/r/run_r_hpc.html)

### Canadian Research Computing Organizations

#### UBC Advanced Research Computing (ARC)

- [Sockeye Technical User Documentation](https://confluence.it.ubc.ca/display/UARC/Using+Sockeye)

#### Digital Research Alliance (Compute Canada)

- [Technical Documentation](https://docs.alliancecan.ca/wiki/Technical_documentation)

## Containers

Similar to virtual machines, containers are a form of virtualization
that packages software and the multiple dependencies required to run
that software into a single container. That container can then be run on
any system that is running the appropriate engine. They are often
lighter and more agile than virtual machines but can include increased
security risks.

### Apptainer (formerly Singularity)

Developed specifically for academic and high-performance computing.
Apptainer avoids some of the security pitfalls of other engines like
Docker at the expense of certain functionalities. Apptainer can only run
a specific container format, but it provides all the necessary tools to
complete conversions.

- [Apptainer Documentation](https://apptainer.org/docs/user/main/)

- [Running Apptainer on an Alliance cluster](https://docs.alliancecan.ca/wiki/Apptainer)

- [Running Apptainer on UBC ARCSockeye](https://confluence.it.ubc.ca/display/UARC/Using+Apptainer+or+Singularity+Containers)

### Podman

- [Podman Documentation](https://docs.podman.io/en/latest/)

### Docker

- [Introduction to Docker](https://ubc-library-rc.github.io/intro-docker)

- [Docker Documentation](https://docs.docker.com/get-started/)

## Image Processing Tools

### Libvips

A multithreaded image processing library that efficiently manages
memory. This library is particularly effective when working with large
images.

- [libvips Documentation](https://www.libvips.org/API/current/)

- [Python Bindings - pyvips](https://github.com/libvips/pyvips)

- [Sharp.js (Node.js) Package](https://sharp.pixelplumbing.com/)

### dcraw

A commonly used library and CLI tool used for decoding RAW image files.
Though minimally maintained, this tool has set the standard for raw
image decoding.

- [Ubuntu Manpage](https://manpages.ubuntu.com/manpages/lunar/en/man1/dcraw.1.html)

### ImageMagick

- [ImageMagick Documentation](https://imagemagick.org/script/command-line-processing.php)

### Pillow (Python)

- [Pillow Documentation](https://pillow.readthedocs.io/en/stable/)
