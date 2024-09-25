---
output-file: index.html
title: Python
---

Python is one of the most popular programming languages in the world. Its low
learning curve paired with a massive ecosystem has made it a powerful tool for
geospatial computing. GIS software like QGIS and ArcGIS, provide the ability to
extend their functionality through Python, while many programming libraries that
have been created to efficiently perform geospatial computing tasks have been
either written in Python, released as Python packages, and/or include
application programming interfaces (APIs) that coherently communicate with
Python code.

If you need recommendations for installing and getting started with Python on
your local machine, see
[Getting Started with Conda, Virtual Environments, and Python](https://ubc-geography.github.io/computing-resources/development-environments/conda-getting-started.html).

The following resources will provide general introductions to Python and its
applications within data science, so any of them can be useful for learning the
basics of Python.

- [Software Carpentry - Programming with Python](https://swcarpentry.github.io/python-novice-inflammation/)

- [Software Carpentry - Plotting and Programming in Python](https://swcarpentry.github.io/python-novice-gapminder/)

- _Python Crash Course_ : [UBC Library](https://go.exlibris.link/XmblT6hZ) |
  [WorldCat](https://search.worldcat.org/title/1346554335)

- _Python All-in-One for Dummies_ :
  [UBC Library](https://go.exlibris.link/fCvpqT4V) |
  [WorldCat](https://search.worldcat.org/title/1425790830)

- _Modern Python Cookbook_ : [UBC Library](https://go.exlibris.link/MTHqzhWG) |
  [WorldCat](https://search.worldcat.org/title/1451040599)

- _Python Tools for Scientists_ :
  [UBC Library](https://go.exlibris.link/7MxPJqXz) |
  [WorldCat](https://search.worldcat.org/title/1347226857)

- _Data Science Fundamentals with R, Python, and Open Data_ :
  [UBC Library](https://go.exlibris.link/kz6Z0BfH) |
  [WorldCat](https://search.worldcat.org/title/1409031863)

## Geospatial Books

- [Carpentries Incubator - Introduction to Geospatial Raster and Vector Data with Python](https://carpentries-incubator.github.io/geospatial-python/)

- _[Geographic Data Science with Python](https://geographicdata.science/book/intro.html)_

- _[Python for Geographic Data Analysis](https://pythongis.org/)_

- [Project Pythia](https://projectpythia.org/)

- _Learning Geospatial Analysis with Python_ :
  [UBC Library](https://go.exlibris.link/JbW0Xp9n) |
  [WorldCat](https://search.worldcat.org/title/1412008153)

- _GIS Algorithms_ : [UBC Library](https://go.exlibris.link/88SQHd9H) |
  [WorldCat](https://search.worldcat.org/title/960087192)

- _Python for Geospatial Data Analysis_ :
  [UBC Library](https://go.exlibris.link/LtW84CTr) |
  [WorldCat](https://search.worldcat.org/title/1348493378)

- _[Geocomputation with Python](https://py.geocompx.org/)_

- _Applied Geospatial Data Science with Python_ :
  [UBC Library](https://go.exlibris.link/6dc1QZpC) |
  [WorldCat](https://search.worldcat.org/title/1369508190)

- _Mastering Geospatial Analysis with Python_ :
  [UBC Library](https://go.exlibris.link/xvlQ7PxR) |
  [WorldCat](https://search.worldcat.org/title/1038802233)

- _Machine Learning on Geographical Data Using Python_ :
  [UBC Library](https://go.exlibris.link/BVwZzHLb) |
  [WorldCat](https://search.worldcat.org/title/1336986830)

### Extending GIS Software

- _A Geographer's Guide to Computing Fundamentals: Python in ArcGIS Pro_ :
  [UBC Library](https://go.exlibris.link/ldtg8mDF) |
  [WorldCat](https://search.worldcat.org/title/1349563332)

- _Python for ArcGIS Pro_ : [UBC Library](https://go.exlibris.link/M4qHpt5M) |
  [WorldCat](https://search.worldcat.org/title/1313386247)

- _Advanced Python Scripting for ArcGIS Pro_ :
  [UBC Library](https://go.exlibris.link/BdWmpYFT) |
  [WorldCat](https://search.worldcat.org/title/1194955062)

- _Mastering Geospatial Development with QGIS 3_ :
  [UBC Library](https://go.exlibris.link/gsFBlwzR) |
  [WorldCat](https://search.worldcat.org/title/1091368567)

- _QGIS Python Programming Cookbook_ :
  [UBC Library](https://go.exlibris.link/M6kWzbVK) |
  [WorldCat](https://search.worldcat.org/title/983204812)

## Geospatial Libraries/Packages

A relatively comprehensive list of packages can be found in the Python section
of [Awesome Geospatial](https://github.com/sacridini/Awesome-Geospatial#python).

Many of the packages included in that list provide powerful, easy-to-use
functionalities around GDAL. If you need to write code that directly interacts
with GDAL, Python bindings are provided, which can be explored through the
[GDAL documentation](https://gdal.org/api/python_bindings.html).

You may also find some other helpful packages listed in
[Python for Data Science - Geodata](https://www.python4data.science/en/latest/data-processing/geodata.html).

## Interactive Visualizations and Dashboards

Dashboard libraries enable you to create interactive visualizations from either
Python code or Jupyter Notebooks, which can be hosted on sparsely-resourced
servers and shared as web applications. You can find information about some of
the most popular libraries at
[PyViz - Dashboarding tools](https://pyviz.org/dashboarding/).

Resources for developing interactive maps via a dashboarding library are listed
below:

- [Voilà & Voici - ipyleaflet](https://ipyleaflet.readthedocs.io/en/latest/index.html)

- [Shiny for Python - ipyleaflet](https://shiny.posit.co/py/components/outputs/map-ipyleaflet/index.html)

- [Displaying Interactive Maps in Streamlit](https://docs.kanaries.net/topics/Streamlit/streamlit-map)

- [Dash - Plotly Maps](https://plotly.com/python/maps/)

- [Panel - Windturbine example](https://panel.holoviz.org/gallery/windturbines.html)
  &
  [hvPlot - Geographic data](https://hvplot.holoviz.org/user_guide/Geographic_Data.html)

Alternatively, libraries like [Voici](https://voici.readthedocs.io/en/latest/)
can similarly convert notebooks to interactive applications, but rather than
running the Python code on a server, Voici shifts computation off of the server
and into a user's web browser using WebAssembly (WASM) and a static webpage.
This makes hosting the application virtually free via services like GitHub Pages
while also making it easier to manage and preserve. The crucial downside to note
is that user's with poor internet connections and/or limited hardware will
struggle to run the applications, especially those that include large datasets
and long, resource-intensive computations.

## Code Quality Tools

Each of the tools listed below can be easily integrated with most development
environments and set up to run automatically. When working with Jupyter
Notebooks, we strongly encourage you to install
[nbqa](https://nbqa.readthedocs.io/en/latest/index.html) alongside these tools
in order to ensure code quality within your notebooks.

### Formatting

Sometimes writing code can get a bit messy. Formatters, like black, can
automatically reformat your code to make it cleaner and easier to read while
following a set of standards and best practices.

- [black Documentation](https://black.readthedocs.io/en/stable/)

### Linting

Using a static analysis tool, or linter, is a common best practice among
programmers that helps in identifying and fixings mistakes when writing code by
ensuring that you follow the correct syntax and a guiding set of best practices.

- [flake8 Documentation](https://flake8.pycqa.org/en/latest/)

### Type Checking

While Python is inherently a dynamically typed language, meaning you the
programmer don't have to worry about the data types of each variable, static
types can be helpful for reducing bugs when writing complex scripts or programs.
Mypy enables programmers to annotate types into their code and returns a helpful
error when those types aren't explicitly followed.

- [mypy Documentation](https://mypy.readthedocs.io/en/stable/)

### Testing Framework

Similar to type checking, unit testing can be a helpful tool when writing large
and complex scripts or programs. Testing frameworks, like pytest, which is
included in Python's standard library, enable you to define tests that can run
over your functions and ensure they are following expected behavior in a range
of practical scenarios.

- [pytest Documentation](https://docs.pytest.org/en/7.3.x/)
