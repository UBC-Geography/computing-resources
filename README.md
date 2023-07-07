# Geography Computing Resources & Documentation

This repository includes a listing of computing resources and accompanying documentation that can be helpful in familiarizing
oneself with various tools and software that are used in Geography research, instruction, and learning.

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

-   [Arts ISIT Video Tutorials](https://isit.web.arts.ubc.ca/video-tutorial-introduction-to-ubc-cms/)

-   [IThemes Tutorials](https://ithemes.com/tutorials/)

-   [Arts ISIT WordPress Resources](https://isit.arts.ubc.ca/resources/)

-   [WordPress Clinics at CTLT](https://events.ctlt.ubc.ca/?s=wordpress)

### UBC Blogs

-   [UBC Blogs vs. UBC CMS](https://support.cms.ubc.ca/cms-manual/getting-started/differences-between-ubc-cms-and-ubc-blogs/)

-   [UBC Blogs FAQ](https://blogs.ubc.ca/faq/)

-   [UBC Blogs Video Tutorials](https://wiki.ubc.ca/UBC_Blogs_Screencasts)

-   [UBC Blogs Instructor Guide](https://lthub.ubc.ca/guides/ubc-blogs-instructor-guide/)

### UBC CMS

-   [UBC CMS Manual](https://support.cms.ubc.ca/cms-manual/)

### Cloud Hosting

-   [UBC IT Shared Hosting](https://it.ubc.ca/services/web-servers-storage/shared-web-hosting)

-   [WordPress Documentation](https://wordpress.org/documentation/)

-   [WordPress 101 -- Video Course](https://learning.oreilly.com/videos/wordpress-101/9781800566415/?sso_link=yes&sso_link_from=univ-british-columbia)

-   [WordPress: The Missing Manual](https://gw2jh3xr2c.search.serialssolutions.com/log?L=GW2JH3XR2C&D=OODEK&J=TC_039927965&P=Link&PT=Redirector&A=WordPress%3A+The+Missing+Manual%2C+3rd+Edition&H=c8a3787037&U=https%3A%2F%2Fgo.oreilly.com%2Funiv-british-columbia%2Fhttps%3A%2F%2Flearning.oreilly.com%2Flibrary%2Fview%2F%7E%2F9781492074151%2F%3Far)

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

-   [Quarto Webinars](https://mint.westdri.ca/tools/quarto_webinar.html)

-   [Quarto Documentation](https://quarto.org/docs/guide/)

### R Markdown (R)

Developed by the company behind RStudio, R Markdown provides an
authoring framework that enables code to be rendered alongside Markdown
and published in multiple formats. See Quarto for a successor to R
Markdown. Note: HTML files rendered via R Markdown use inline scripts
and CSS, which can create sometimes unnecessarily large files, but they
ensure that the file displays consistently without external files.

-   [R Markdown Documentation](https://rmarkdown.rstudio.com/lesson-1.html)

### Jekyll (Ruby)

One of the most used static site generators. This SSG integrates
smoothly with GitHub Pages to quickly render websites directly from a
GitHub repository. Due to its wide adoption, it also includes a wide
range of open-source themes that can be used to customize the style of a
website.

-   [Introduction to Jekyll](https://ubc-library-rc.github.io/intro-jekyll)

-   [Intermediate Jekyll](https://ubc-library-rc.github.io/intermediate-Jekyll/)

-   [Building a project website with Jekyll and GitHub Pages](https://ubc-library-rc.github.io/intro-project-sites/)

-   [Jekyll Documentation](https://jekyllrb.com/docs/)

## Digital Exhibit Tools

Storing and presenting digital assets, like images, audio, and video
files, can be easily managed via content management systems and static
site generators that specialize in digital exhibits.

-   [Survey of Digital Exhibit Tools](https://ubc-library-rc.github.io/digital-exhibits-survey/)

### Omeka Classic & Omeka-S

Omeka Classic is targeted towards small, individually developed
projects, while Omeka-S focuses on developing larger scale,
institutional-wide repositories with multiple collections or projects.
Both are considered web applications as they include content management
systems that provide an easy-to-use interface for developing and
managing digital exhibits.

-   [Building Digital Exhibits with Omeka](https://github.com/ubc-library-rc/intro-omeka)

-   [Omeka: A User's Guide: Introduction](https://guides.library.illinois.edu/omeka/intro)

#### Cloud Hosting

-   [UBC IT Shared Hosting](https://it.ubc.ca/services/web-servers-storage/shared-web-hosting)

-   [Omeka Classic Documentation](https://omeka.org/classic/docs/)

-   [Omeka-S Documentation](https://omeka.org/s/docs/user-manual/)

### CollectionBuilder

Lacking a content management system, CollectionBuilder centers the
development and management of digital exhibits around CSVs and Markdown.
Built as a theme around a static site generator (Jekyll),
CollectionBuilder creates digital exhibits as fast and easy-to-preserve
websites.

-   [CollectionBuilder Documentation](https://collectionbuilder.github.io/cb-docs/)

## Research Data Management (RDM)

-   [Research Data Management -- File Naming](https://ubc-library-rc.github.io/rdm/content/01_file_naming.html)

-   [Research Data Management -- File Formats](https://ubc-library-rc.github.io/rdm/content/02_file_formats.html)

-   [Research Data Management Video -- Part 1](https://www.youtube.com/watch?v=TxYlHMieXAM)

-   [Research Data Management Video -- Part 2](https://www.youtube.com/watch?v=q5eXXps1o04)

### GIS-Related Standards

-   [Open Geospatial Consortium Standards](https://www.ogc.org/standard/sfs/)

## Python

### Virtual Environment Manager

When using modules not found in Python's standard library, you should
always install and run the module packages within a virtual environment.
This isolates your code and packages from any globally installed Python
packages and ensures you are using the appropriate package version for
your code. 

#### conda

conda is an extremely powerful tool for both managing environments and packages. Using `conda install`
provides the ability to install a range of powerful packages that aren't available via Python's `pip`.
If you are very new to Python and still getting comfortable, try getting confident creating virtual 
environments and installing packages via venv and pip before using conda.

If you need to install conda on your device, we suggest using the link below to install it using Miniconda.

-   [Miniconda, a minimal installer for conda](https://docs.conda.io/en/latest/miniconda.html)

-   [conda User Guide](https://docs.conda.io/projects/conda/en/stable/user-guide/index.html)

#### venv and virtualenv

venv is a lightweight module that has been included with base installations of Python
since version 3.3 and enables you to quickly setup and manage virtual environments for your project. 
virtualenv is a more powerful alternative to venv, but unlike venv it needs to be installed
separtely via pip. Both modules lack the same level of functionality as conda, but they can be helpful tools for those
who are still getting comfortable with Python or don't need conda's added functionalities.

-   [venv Documentation](https://docs.python.org/3/library/venv.html)

-   [virtualenv Documentation](https://virtualenv.pypa.io/en/latest/)

### Linting

Using a static analysis tool, or linter, is a common best practice among
programmers that helps in identifying and fixings mistakes when writing code by
ensuring that you follow the correct syntax and a guiding set of best
practices.

-   [flake8 Documentation](https://flake8.pycqa.org/en/latest/)

### Type Checking

While Python is inherently a dynamically typed language, meaning you the
programmer don't have to worry about the data types of each variable,
static types can be helpful for reducing bugs when writing complex
scripts or programs. Mypy enables programmers to annotate types into
their code and returns a helpful error when those types aren't
explicitly followed.

-   [mypy Documentation](https://mypy.readthedocs.io/en/stable/)

### Formatting

Sometimes writing code can get a bit messy. Formatters, like black, can
automatically reformat your code to make it cleaner and easier to read
while following a set of standards and best practices.

-   [black Documentation](https://black.readthedocs.io/en/stable/)

### Testing Framework

Similar to type checking, unit testing can be a helpful tool when
writing large and complex scripts or programs. Testing frameworks, like
pytest, which is included in Python's standard library, enable you to
define tests that can run over your functions and ensure they are
following expected behavior in a range of practical scenarios.

-   [pytest Documentation](https://docs.pytest.org/en/7.3.x/)

### Geospatial Libraries/Packages

-   [Awesome Geospatial - Python](https://github.com/sacridini/Awesome-Geospatial#python)

### Other Related Libraries/Packages

#### SciPy

-   [SciPy Documentation](https://docs.scipy.org/doc/scipy/)

#### Numpy

-   [NumPy Documentation](https://numpy.org/doc/stable/)

#### pandas

-   [pandas Documentation](https://pandas.pydata.org/docs/)

#### GDAL Bindings

-   [GDAL Python Documentation](https://gdal.org/api/python_bindings.html)

#### scikit-learn

-   [scikit-learn Documentation](https://scikit-learn.org/stable/user_guide.html)

#### matplotlib

-   [matplotlib User Guide](https://matplotlib.org/stable/users/index)

#### seaborn

-   [seaborn Tutorial](https://seaborn.pydata.org/tutorial.html)

#### bokeh

-   [bokeh Documentation](https://docs.bokeh.org/en/latest/docs/user_guide.html)

#### plotly

-   [plotly Fundamentals](https://plotly.com/python/plotly-fundamentals/)

#### Folium

-   [Folium Documentation](https://python-visualization.github.io/folium/)

#### Dask

-   [Dask Documentation](https://docs.dask.org/en/stable/)

## R

-   [Introduction to R for Spatial Data Science](https://rspatial.org/intr/index.html)

-   [Spatial Data Science with Applications in R](https://r-spatial.org/book/)

### Linting

Using a static analysis tool, or linter, is a common best practice among
programmers that helps identify mistakes when writing code by ensuring
that you follow the correct syntax and a guiding set of best practices.

-   [lintr Documentation](https://lintr.r-lib.org/)

### Formatting

Sometimes writing code can get a bit messy. Formatters, like styler, can
automatically reformat your code to make it cleaner and easier to read
while following a set of standards and best practices.

Note: RStudio includes a formatting tool via Code \> Reformat Code

-   [styler Documentation](https://styler.r-lib.org/)

### Benchmarking

When writing code, there is often a wide array of ways in which a task
can be completed. Benchmarking your functions can help you find the most
efficient approach possible. This is particularly important when writing
scripts and programs that will be used on large datasets and/or on high
performance computers.

-   [bench Documentation](https://cran.r-project.org/web/packages/bench/bench.pdf)

### Geospatial Libraries/Packages

-   [CRAN Task View: Analysis of Spatial Data](https://cran.r-project.org/web/views/Spatial.html)

-   [Awesome Geospatial - R](https://github.com/sacridini/Awesome-Geospatial#r)

### Other Related Libraries/Packages

#### trajectories

-   [trajectories: Classes and Methods for Trajectory Data](https://cran.r-project.org/web/packages/trajectories/vignettes/article.pdf)

-   [trajectories Reference Manual](https://cran.r-project.org/web/packages/trajectories/trajectories.pdf)

#### xts

-   [xts: Extensible Time Series](https://cran.r-project.org/web/packages/xts/vignettes/xts.pdf)

-   [xts Reference Manual](https://cran.r-project.org/web/packages/xts/xts.pdf)

#### zoo

-   [zoo: An S3 Class and Methods for Indexed Totally Ordered Observations](https://cran.r-project.org/web/packages/zoo/vignettes/zoo.pdf)

-   [zoo Reference Manual](https://cran.r-project.org/web/packages/zoo/zoo.pdf)

#### tidygraph

-   [tidygraph Reference Manual](https://cran.r-project.org/web/packages/tidygraph/tidygraph.pdf)

#### proj4

-   [proj4 Reference Manual](https://cran.r-project.org/web/packages/proj4/proj4.pdf)

#### dplyr

-   [Introduction to dplyr](https://cran.r-project.org/web/packages/dplyr/vignettes/dplyr.html)

-   [dpylr Documentation](https://dplyr.tidyverse.org/)

-   [dpylr Reference Manual](https://cran.r-project.org/web/packages/dplyr/dplyr.pdf)

#### tidyr

-   [tidyr Documentation](https://tidyr.tidyverse.org/)

-   [tidyr Reference Manual](https://cran.r-project.org/web/packages/tidyr/tidyr.pdf)

#### CAST

-   [Introduction to CAST](https://hannameyer.github.io/CAST/articles/cast01-CAST-intro.html)

-   [CAST Reference Manual](https://cran.r-project.org/web/packages/CAST/CAST.pdf)

#### mlr3Spatial

-   [Spatial Data in the mlr3 Ecosystem](https://mlr-org.com/gallery/technical/2023-02-27-land-cover-classification/)

-   [mlr3Spatial Reference Manual](https://cran.r-project.org/web/packages/mlr3spatial/mlr3spatial.pdf)

#### performanceEstimation

-   [performanceEstimation GitHub README](https://github.com/ltorgo/performanceEstimation/blob/master/README.md)

-   [performanceEstimation Reference Manual](https://cran.r-project.org/web/packages/performanceEstimation/performanceEstimation.pdf)

#### plotly

-   [Interactive web-based data visualization with R, plotly, and shiny](https://plotly-r.com/)

-   [plotly Reference Manual](https://plotly-r.com/)

## JavaScript

### GIS Libraries/Packages

#### Web Mapping

-   [Awesome Geospatial -- Web Mapping](https://github.com/sacridini/Awesome-Geospatial#web-map-development)

##### Leaflet

-   [Web mapping with LeafletJS](https://ubc-library-rc.github.io/gis-intro-leaflet/)

-   [Leaflet Tutorials](https://leafletjs.com/examples.html)

##### Mapbox

-   [Mapbox GL JS Guide](https://docs.mapbox.com/mapbox-gl-js/guides/)

#### Visualizations

-   [D3 Documentation](https://github.com/d3/d3/wiki)

-   [Observable Plot Documentation](https://observablehq.com/plot/getting-started)

#### Observable JS

-   [Observable Documentation](https://observablehq.com/@observablehq/documentation?collection=@observablehq/documentation)

## Jupyter Notebooks

-   [JupyterHub Instructor Guide](https://lthub.ubc.ca/guides/jupyterhub-instructor-guide/)

### GIS Packages/Libraries

#### Mapping

-   [ipyleaflet Documentation](https://ipyleaflet.readthedocs.io/en/latest/index.html)

## RStudio

-   [RStudio UserGuide](https://docs.posit.co/ide/user/ide/get-started/)

## Visual Studio Code

-   [VS Code Overview in Setting Up a Dev Environment](https://ubc-library-rc.github.io/intro-development-environment/content/02-1.VSCode.html)

-   [VS Code Documentation](https://code.visualstudio.com/docs)

-   [Using Git source control in VSCode](https://code.visualstudio.com/docs/sourcecontrol/overview)

### Helpful Extensions

#### Remote Development

-   [Remote Development Extension Overview](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack)

#### Jupyter

-   [Jupyter Extension Overview](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter)

#### Quarto

-   [Quarto Extension Overview](https://marketplace.visualstudio.com/items?itemName=quarto.quarto)

#### Python

-   [Python in VS Code Documentation](https://code.visualstudio.com/docs/languages/python)

-   [Python Extension Overview](https://marketplace.visualstudio.com/items?itemName=ms-python.python)

#### R

-   [R in VS Code Documentation](https://code.visualstudio.com/docs/languages/r)

-   [R Extension Overview](https://marketplace.visualstudio.com/items?itemName=REditorSupport.r)

## Git & GitHub

-   [Introduction to Git and GitHub](https://ubc-library-rc.github.io/intro-git/)

-   [Git Tutorial and Workshops](https://mint.westdri.ca/git/)

-   [GitHub Desktop Documentation](https://docs.github.com/en/desktop/installing-and-configuring-github-desktop/overview/getting-started-with-github-desktop)

-   [GitHub Documentation](https://docs.github.com/en)

-   [GitHub InstructorGuide](https://lthub.ubc.ca/guides/github-instructor-guide/)

-   [Building a project website with Jekyll and GitHub Pages](https://ubc-library-rc.github.io/intro-project-sites/)

-   [Git and Jupyter Notebooks: The Ultimate Guide](https://www.reviewnb.com/git-jupyter-notebook-ultimate-guide)

## SQL Databases

-   [How to create and access MySQL and PostgreSQL databases on DRI systems - Video](https://youtu.be/3uHSXXQwJpQ)

### PostgreSQL

#### Hosting

##### Alliance

-   [Database Servers -- Cedar PostreSQL](https://docs.alliancecan.ca/wiki/Database_servers#Cedar_PostgreSQL_server)

##### Cloud / SaaS Providers

-   [MicrosoftAzure](https://azure.microsoft.com/en-ca/products/postgresql/)

-   [AWS](https://aws.amazon.com/rds/postgresql/)

-   [Google Cloud](https://cloud.google.com/sql/docs/postgres)

-   [Supabase](https://supabase.com/docs/guides/database)

-   [Railway](https://docs.railway.app/databases/postgresql)

#### GIS Extensions / Libraries

-   [PostGIS](https://postgis.net/documentation/)

-   [pgRouting](https://docs.pgrouting.org/latest/en/pgRouting-introduction.html)

### MySQL

#### Hosting

##### Alliance

-   [Database Servers -- Cedar MySQL](https://docs.alliancecan.ca/wiki/Database_servers#Cedar_MySQL_server)

##### Cloud / SaaS Providers

-   [Microsoft Azure](https://azure.microsoft.com/en-ca/products/mysql/)

-   [AWS](https://aws.amazon.com/rds/mysql/)

-   [Google Cloud](https://cloud.google.com/sql/docs/mysql)

-   [PlanetScale](https://planetscale.com/docs)

-   [Railway](https://docs.railway.app/databases/mysql)

#### GIS Extensions / Libraries

-   [MySQL Spatial](https://dev.mysql.com/doc/refman/8.0/en/spatial-analysis-functions.html)

## Unix Shells & Command Line Interfaces (CLI)

-   [Introduction to the UNIX Shell](https://ubc-library-rc.github.io/intro-shell/)

-   [Intermediate UNIX Shell](https://ubc-library-rc.github.io/advanced-shell/)

-   [Bash Course and Webinar](https://mint.westdri.ca/bash/)

-   [Intro to Linux and the Bash Shell in HPC Environments](https://confluence.it.ubc.ca/display/UARC/Introduction+to+Linux+and+Using+the+Command+Line+Interface)

-   [Intro to Linux Shell -- Video Lecture](https://www.youtube.com/watch?v=eLF598YqbFw)

## High Performance Computing (HPC)

-   [Introduction to Compute Canada (Alliance) Video](https://www.youtube.com/watch?v=hWkWAaNBILs)

-   [Intro to Linux and the Bash Shell in HPC Environments](https://confluence.it.ubc.ca/display/UARC/Introduction+to+Linux+and+Using+the+Command+Line+Interface)

-   [Research Computing Bootcamp Videos](https://www.ualberta.ca/information-services-and-technology/research-computing/bootcamps.html?1=HPC)

-   [Geospatial Analysis with HPC Video](https://youtu.be/wRmRnVMjKXM)

### Jupyter in HPC

-   [Alliance Documentation](https://docs.alliancecan.ca/wiki/JupyterHub)

### Python in HPC

-   [Working with the Python Dask (Parallelization) Library Video](https://youtu.be/uGy5gT2vLdI)

### R in HPC

-   [Introduction to HPC in R Webinar](https://mint.westdri.ca/r/intro_hpc.html)

-   [High-performance R Tutorial](https://mint.westdri.ca/r/run_r_hpc.html)

### Canadian Research Computing Organizations

#### UBC Advanced Research Computing (ARC)

-   [Sockeye Technical User Documentation](https://confluence.it.ubc.ca/display/UARC/Using+Sockeye)

#### Digital Research Alliance (Compute Canada)

-   [Technical Documentation](https://docs.alliancecan.ca/wiki/Technical_documentation)

#### For Instruction / Student Use

-   [UBC LT Support](https://lthub.ubc.ca/initiatives/high-performance-computing/)

-   [Introduction to Syzygy (JupyterHub)](https://intro.syzygy.ca/)

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

-   [Apptainer Documentation](https://apptainer.org/docs/user/main/)

-   [Running Apptainer on an Alliancecluster](https://docs.alliancecan.ca/wiki/Apptainer)

-   [Running Apptainer on UBC ARCSockeye](https://confluence.it.ubc.ca/display/UARC/Using+Apptainer+or+Singularity+Containers)

### Podman

-   [Podman Documentation](https://docs.podman.io/en/latest/)

### Docker

-   [Introduction to Docker](https://ubc-library-rc.github.io/intro-docker)

-   [Docker Documentation](https://docs.docker.com/get-started/)

## Image Processing Tools

### Libvips

A multithreaded image processing library that efficiently manages
memory. This library is particularly effective when working with large
images.

-   [libvips Documentation](https://www.libvips.org/API/current/)

-   [Python Bindings - pyvips](https://github.com/libvips/pyvips)

-   [Sharp.js (Node.js) Package](https://sharp.pixelplumbing.com/)

### dcraw

A commonly used library and CLI tool used for decoding RAW image files.
Though minimally maintained, this tool has set the standard for raw
image decoding.

-   [Ubuntu Manpage](https://manpages.ubuntu.com/manpages/lunar/en/man1/dcraw.1.html)

### ImageMagick

-   [ImageMagick Documentation](https://imagemagick.org/script/command-line-processing.php)

### Pillow (Python)

-   [Pillow Documentation](https://pillow.readthedocs.io/en/stable/)