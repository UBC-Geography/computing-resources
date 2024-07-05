---
output-file: index.html
title: R
---

Alongside Python, R is one of the commonly used programming languages in
geography research due in part to the large collection of geospatial packages
that have been developed with it along with it's broad adoption for scientific
computing.

The easiest and most recommended approach for getting started with R is to
download the installer from CRAN:

- [Windows](https://cran.r-project.org/bin/windows/base/)

- [Mac OS](https://cran.r-project.org/bin/macosx/)

- [Linux](https://cran.r-project.org/bin/linux/)

The following resources will provide general introductions to R and its
applications within data science, so any of them can be useful for learning the
basics of R.

- [Software Carpentry - Programming with R](https://swcarpentry.github.io/r-novice-inflammation/)

- [Software Carpentry - R for Reproducible Scientific Analysis](https://swcarpentry.github.io/r-novice-gapminder/)

- _R in Action_ : [UBC Library](https://go.exlibris.link/P6rJdt9g) |
  [WorldCat](https://search.worldcat.org/title/1325721232)

- _R for the Rest of Us_ : [UBC Library](https://go.exlibris.link/CryW41CM) |
  [WorldCat](https://search.worldcat.org/title/1431119628)

- _R for Data Science_ : [UBC Library](https://go.exlibris.link/FW9jGNqj) |
  [WorldCat](https://search.worldcat.org/title/1392138200)

- _Statistical Analysis with R Essentials for Dummies_ :
  [UBC Library](https://go.exlibris.link/Stf1fNCy) |
  [WorldCat](https://search.worldcat.org/title/1430211695)

- _R 4 Data Science Quick Reference_ :
  [UBC Library](https://go.exlibris.link/PLPKnlK4) |
  [WorldCat](https://search.worldcat.org/title/1349468003)

- _Data Science Fundamentals with R, Python, and Open Data_ :
  [UBC Library](https://go.exlibris.link/kz6Z0BfH) |
  [WorldCat](https://search.worldcat.org/title/1409031863)

- [Quick-R](https://www.statmethods.net/)

- [R-bloggers](https://www.r-bloggers.com/)

## Geospatial Books

- _[Geographic Data Science with R: Visualizing and Analyzing Environmental Change](https://doi.org/10.1201/9781003326199)_

- _Learning R for Geospatial Analysis_ :
  [UBC Library](https://go.exlibris.link/nMcRqq29) |
  [WorldCat](https://search.worldcat.org/title/900886812)

- _[Introduction to R for Spatial Data Science](https://rspatial.org/intr/index.html)_

- _[Spatial Data Science with Applications in R](https://r-spatial.org/book/)_

- _Geocomputation with R_ : [UBC Library](https://go.exlibris.link/hS3B926C) |
  [WorldCat](https://search.worldcat.org/title/1090540543)

- _Remote Sensing and Digital Image Processing with R_ :
  [UBC Library](https://go.exlibris.link/JMr62B9N) |
  [WorldCat](https://search.worldcat.org/title/1378724739)

- _Surveying with Geomatics and R_ :
  [UBC Library](https://go.exlibris.link/yzsrpMzv) |
  [WorldCat](https://search.worldcat.org/title/1273700848)

### Extending GIS Software

- _Hands-On Geospatial Analysis with R and QGIS_ :
  [UBC Library](https://go.exlibris.link/c835FCNj) |
  [WorldCat](https://search.worldcat.org/title/1084488168)

## Geospatial Libraries/Packages

A relatively comprehensive list of packages can be found in the R section of
[Awesome Geospatial](https://github.com/sacridini/Awesome-Geospatial#R).

For a closer analysis on some of the most popular R packages for spatial data
analysis, consider reviewing the following journal article.

- [R Packages for Analyzing Spatial Data: A Comparative Case Study with Areal Data](https://doi.org/10.1111/gean.12319)

Additionally, you can identify packages from the following CRAN task views.

- [CRAN Task View: Analysis of Ecological and Environmental Data](https://cran.r-project.org/web/views/Environmetrics.html)

- [CRAN Task View: Hydrological Data and Modeling](https://cran.r-project.org/web/views/Hydrology.html)

- [CRAN Task View: Analysis of Spatial Data](https://cran.r-project.org/web/views/Spatial.html)

- [CRAN Task View: Handling and Analyzing Spatio-Temporal Data](https://cran.r-project.org/web/views/SpatioTemporal.html)

## Interactive Visualizations and Dashboards

Dashboard libraries enable you to create interactive visualizations from your R
code, which can be hosted on sparsely-resourced servers and shared as web
applications.

- [Shiny for R - Getting Started](https://shiny.posit.co/r/getstarted/shiny-basics/lesson1/index.html)

- [Shiny for R - Leaflet: Interactive Web Maps with R](https://posit.co/blog/leaflet-interactive-web-maps-with-r/)

- _Mastering Shiny_ : [UBC Library](https://go.exlibris.link/BST471rL) |
  [WorldCat](https://search.worldcat.org/title/1235778006)

- [Dash R User Guide](https://dash.plotly.com/r)

- [Dash - Plotly Maps](https://plotly.com/r/maps/)

## Code Quality Tools

### Formatting

Sometimes writing code can get a bit messy. Formatters, like styler, can
automatically reformat your code to make it cleaner and easier to read while
following a set of standards and best practices.

::: {.callout-note}

RStudio includes a formatting tool via Code \> Reformat Code

:::

- [styler Documentation](https://styler.r-lib.org/)

### Linting

Using a static analysis tool, or linter, is a common best practice among
programmers that helps identify mistakes when writing code by ensuring that you
follow the correct syntax and a guiding set of best practices.

- [lintr Documentation](https://lintr.r-lib.org/)

### Testing Framework

Similar to type checking, unit testing can be a helpful tool when writing large
and complex scripts or programs. Testing frameworks enable you to define tests
that can run over your functions and ensure they are following expected behavior
in a range of practical scenarios.

- [testthat Documentation](https://testthat.r-lib.org/)

### Benchmarking

When writing code, there is often a wide array of ways in which a task can be
completed. Benchmarking your functions can help you find the most efficient
approach possible. This is particularly important when writing scripts and
programs that will be used on large datasets and/or on high performance
computers.

- [bench Documentation](https://cran.r-project.org/web/packages/bench/bench.pdf)
