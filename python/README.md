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
[Getting Started with Conda, Virtual Environments, and Python](https://UBC-Geography.github.io/development-environments/conda-getting-started).

- _[Python for Geographic Data Analysis](https://pythongis.org/)_

- _[Python Crash Course](https://go.exlibris.link/XmblT6hZ)_

- _[Python All-in-One for Dummies](https://learning.oreilly.com/library/view/python-all-in-one-for/9781394236152/)_

- _[Python Tools for Scientists](https://go.exlibris.link/7MxPJqXz)_

- _[Data Science Fundamentals with R, Python, and Open Data](https://learning.oreilly.com/library/view/data-science-fundamentals/9781394213245/)_

## Geospatial Books

- _[Geographic Data Science with Python](https://geographicdata.science/book/intro.html)_

- _[Learning Geospatial Analysis with Python](https://learning.oreilly.com/library/view/learning-geospatial-analysis/9781837639175/)_

- _[GIS Algorithms](http://resolve.library.ubc.ca/cgi-bin/catsearch?bid=10279472)_

- _[Python for Geospatial Data Analysis](https://go.exlibris.link/LtW84CTr)_

- _[Geocomputation with Python](https://py.geocompx.org/)_

- _[Applied Geospatial Data Science with Python](https://go.exlibris.link/6dc1QZpC)_

- _[Mastering Geospatial Analysis with Python: Explore GIS Processing and Learn to Work with GeoDjango, CARTOframes and MapboxGL-Jupyter](https://go.exlibris.link/gsFBlwzR)_

- _[Machine Learning on Geographical Data Using Python Introduction into Geodata with Applications and Use Cases](http://resolve.library.ubc.ca/cgi-bin/catsearch?bid=12453975)_

### Extending GIS Software

- _[A Geographer's Guide to Computing Fundamentals: Python in ArcGIS Pro](http://resolve.library.ubc.ca/cgi-bin/catsearch?bid=12441298)_

- _[Python for ArcGIS Pro](https://go.exlibris.link/M4qHpt5M)_

- _[Advanced Python Scripting for ArcGIS Pro](http://resolve.library.ubc.ca/cgi-bin/catsearch?bid=11878622)_

- _[Mastering Geospatial Development with QGIS 3](https://go.exlibris.link/gsFBlwzR)_

- _[QGIS Python Programming Cookbook](https://go.exlibris.link/M6kWzbVK)_

## Geospatial Libraries/Packages

- [Awesome Geospatial - Python](https://github.com/sacridini/Awesome-Geospatial#python)

- [GDAL Python Documentation](https://gdal.org/api/python_bindings.html)

## Formatting

Sometimes writing code can get a bit messy. Formatters, like black, can
automatically reformat your code to make it cleaner and easier to read while
following a set of standards and best practices.

- [black Documentation](https://black.readthedocs.io/en/stable/)

## Linting

Using a static analysis tool, or linter, is a common best practice among
programmers that helps in identifying and fixings mistakes when writing code by
ensuring that you follow the correct syntax and a guiding set of best practices.

- [flake8 Documentation](https://flake8.pycqa.org/en/latest/)

## Type Checking

While Python is inherently a dynamically typed language, meaning you the
programmer don't have to worry about the data types of each variable, static
types can be helpful for reducing bugs when writing complex scripts or programs.
Mypy enables programmers to annotate types into their code and returns a helpful
error when those types aren't explicitly followed.

- [mypy Documentation](https://mypy.readthedocs.io/en/stable/)

## Testing Framework

Similar to type checking, unit testing can be a helpful tool when writing large
and complex scripts or programs. Testing frameworks, like pytest, which is
included in Python's standard library, enable you to define tests that can run
over your functions and ensure they are following expected behavior in a range
of practical scenarios.

- [pytest Documentation](https://docs.pytest.org/en/7.3.x/)

## Web Frameworks

While Python supports a large number of popular all-purpose web frameworks,
including Django, Flask, and FastAPI, it also supports specialized frameworks
that excel at supporting and sharing geospatial research.

### Interactive Visualizations and Dashboards

- [Voila](https://voila.readthedocs.io/en/stable/index.html) - Developed under
  the Jupyter Project, Voilà is a tool for converting and rendering Jupyter
  notebooks as interactive web applications. These applications can be deployed
  on a private server or via hosting providers like Binder, Railway, or Google
  App Engine.

- [Voici](https://voici.readthedocs.io/en/latest/) - Built by the same team
  behind Voilà, Voici is an experimental tool that can similarly convert
  notebooks to interactive applications, but rather than running the Python
  kernel on a server, Voici shifts computation off of the server and into a
  user's web browser using WebAssembly (WASM) and a static webpage. This makes
  hosting the application virtually free via services like GitHub Pages while
  also making it easier to manage and preserve. The crucial downside to note is
  that user's with poor internet connections and/or limited hardware will
  struggle to run the applications, especially those that include large datasets
  and long, resource-intensive computations.

- [Mercury](https://runmercury.com/)

- [Shiny for Python](https://shiny.posit.co/py/)

- [Streamlit](https://docs.streamlit.io/)

- [Dash](https://dash.plotly.com/)

- [Panel](https://panel.holoviz.org/)

### Geographic Web Frameworks

- [GeoDjango](https://docs.djangoproject.com/en/4.2/ref/contrib/gis/)

## Other Related Libraries/Packages

- [SciPy](https://docs.scipy.org/doc/scipy/)

- [NumPy](https://numpy.org/doc/stable/)

- [pandas](https://pandas.pydata.org/docs/)

- [scikit-learn](https://scikit-learn.org/stable/user_guide.html)

- [matplotlib](https://matplotlib.org/stable/users/index)

- [seaborn](https://seaborn.pydata.org/tutorial.html)

- [bokeh](https://docs.bokeh.org/en/latest/docs/user_guide.html)

- [plotly](https://plotly.com/python/plotly-fundamentals/)

- [Folium](https://python-visualization.github.io/folium/)

- [Dask](https://docs.dask.org/en/stable/)

- [rpy2](https://rpy2.github.io/doc.html)
