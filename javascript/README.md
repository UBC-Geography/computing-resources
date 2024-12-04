---
output-file: index.html
title: JavaScript
---

While JavaScript has fewer applications in geography compared to other languages
like Python and R, it remains a useful skill to develop, particularly for
interacting with Google Earth Engine or creating interactive web maps and
web-based visualizations.

It's important to note that JavaScript code can be executed in various and often
quite different contexts with the most common being web browsers (front-end or
client-side) and runtime engines (back-end or server-side), like Node.js and
Deno. Most applications of JavaScript relevant to geographers occurs in the
former with the use of libraries, like Leaflet, D3.js, and Observable.

The following resources will provide general introductions to JavaScript and its
applications within the context of a web browser, so any of them can be useful
for learning the basics of JavaScript.

- [MDN Web Docs - JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript)

- _[Eloquent JavaScript](https://eloquentjavascript.net/)_

- _JavaScript Essentials for Dummies_ :
  [UBC Library](https://learning.oreilly.com/library/view/javascript-essentials-for/9781394263219/)
  | [WorldCat](https://search.worldcat.org/title/1428261417)

## Geospatial Libraries/Packages

A relatively comprehensive list of libraries that focus on using JavaScript in
the web browser can be found below:

- [Awesome Frontend GIS](https://github.com/joewdavies/awesome-frontend-gis?tab=readme-ov-file#-javascript-libraries)

Additionally, you may find a few more libraries along with packages that run in
Node.js through the following list:

- [Awesome Geospatial - JavaScript](https://github.com/sacridini/Awesome-Geospatial?tab=readme-ov-file#javascript)

### Google Earth Engine (GEE)

The code editor that is built into Google Earth Engine acts as a JavaScript
runtime or playground. Through the code editor, you can write JavaScript scripts
that interact with the Google Earth Engine API to access and analyze data.
Computational resources to the GEE Code Editor may be too limited for some
computational work. In those cases, you can transfer your code to your local
machine and run it from an environment where Node.js and the
[GEE API library](https://github.com/google/earthengine-api) are installed. If
you have Miniforge installed on your machine, you can use the following commands
to quickly set up an environment using `mamba`.

```bash
$ mamba create -n nodejs nodejs
$ mamba activate nodejs
$ npm install --save @google/earthengine
```

Then you can following these
[instructions](https://developers.google.com/earth-engine/guides/npm_install#server-side-authentication-with-a-service-account)
to setup a service account for your Google Cloud Project and authenticate to the
API in your JavaScript script.

- [Google Earth Engine Guides](https://developers.google.com/earth-engine/guides)

- _[Cloud-Based Remote Sensing with Google Earth Engine](https://library.oapen.org/handle/20.500.12657/76709)_

### Web Mapping

Developing interactive maps that can be shared via the web is one of the most
commonly used applications of JavaScript in geography. A few resources and
libraries used for developing web maps are listed in the link below, followed by
resources associated with the four major web mapping libraries.

- [Awesome Geospatial -- Web Mapping](https://github.com/sacridini/Awesome-Geospatial#web-map-development)

UBC Library Research Commons frequently provides workshops on web mapping using
some of the tools listed below. You can find upcoming workshops
[here](https://libcal.library.ubc.ca/calendar/?t=g&q=web%20map&cid=-1&cal=-1&ct=33914,34011&inc=0).

#### Leaflet

The smallest and most popular of the four major JavaScript web mapping
libraries, Leaflet lacks some of the functionalities of comparable libraries,
but provides the best options for quickly rendering small to medium datasets.
For additional functionality, Leaflet can be extended using a wide array of
[plugins](https://leafletjs.com/plugins.html).

- [UBC Library Research Commons - Web Mapping with LeafletJS](https://ubc-library-rc.github.io/gis-intro-leaflet/)

- [Leaflet Tutorials](https://leafletjs.com/examples.html)

#### OpenLayers

While nearly twice as large as Leaflet, OpenLayers includes additional
functionalities and often performs better than Leaflet when working with larger
datasets[^1].

- [OpenLayers Documentation](https://openlayers.org/doc/)

#### Mapbox GL

At a size significantly larger than both OpenLayers and Leaflet, Mapbox GL
includes a wide range of features when rendering maps and is particularly
powerful when rending 3D features. Unlike Leaflet and OpenLayers, Mapbox GL is
not free and open-source meaning that it must be paired with Mapbox's APIs.

- [Mapbox GL JS Guide](https://docs.mapbox.com/mapbox-gl-js/guides/)

#### MapLibre GL JS

MapLibre is a free and open-source fork of Mapbox GL that retains some of the
unique functionalities of Mapbox GL while enabling the usage of alternative
datasets and APIs.

- [MapLibre GL JS Documentation](https://maplibre.org/maplibre-gl-js/docs/)

## Interactive Visualizations and Dashboards

JavaScript excels at creating interactive visualizations, and similar to web
mapping, there is a massive number of libraries that can make development
easier. Resources for a few of the most popular libraries are listed below.

- [D3 Documentation](https://github.com/d3/d3/wiki)

- _D3.js in Action_ :
  [UBC Library](https://learning.oreilly.com/library/view/d3-js-in-action/9781633439177/)
  | [WorldCat](https://search.worldcat.org/title/1050968610)

- [Observable Plot Documentation](https://observablehq.com/plot/getting-started)

- [Deck.gl Documentation](https://deck.gl/docs)

- [Plotly - JavaScript](https://plotly.com/javascript/)

### Observable JS

Observable provides an interactive alternative to Jupyter with computational
work completed within a user's browser rather than on a server. Tools like
Quarto integrate smoothly with Observable.

- [Observable Documentation](https://observablehq.com/@observablehq/documentation?collection=@observablehq/documentation)

- [Quarto - Observable JS](https://quarto.org/docs/interactive/ojs/)

## Code Quality Tools

### Formatting

Sometimes writing code can get a bit messy. Formatters can automatically
reformat your code to make it cleaner and easier to read while following a set
of standards and best practices.

- [Prettier Documentation](https://prettier.io/docs/en/index.html)

### Linting

Using a static analysis tool, or linter, is a common best practice among
programmers that helps in identifying and fixings mistakes when writing code by
ensuring that you follow the correct syntax and a guiding set of best practices.

- [ESLint Documentation](https://eslint.org/docs/latest/)

### Type Checking

Like Python, JavaScript is inherently a dynamically typed language, meaning you
the programmer don't have to worry about the data types of each variable. Static
types can be helpful for reducing bugs when writing complex scripts or programs.
The primary way to add type checking to JavaScript is to actually write in
another programming language, TypeScript, which is a superset of JavaScript.
Another method is to use JSDoc, which enables you to annotate your JavaScript
code with types. The TypeScript transpiler then uses those comments to check
your types and return errors as it finds them.

- [JSDoc Documentation](https://jsdoc.app/)

- [TypeScript Documentation - JSDoc Reference](https://www.typescriptlang.org/docs/handbook/jsdoc-supported-types.html?)

### Testing Framework

Similar to type checking, unit testing can be a helpful tool when writing large
and complex scripts or programs. Jest enables you to define tests that can run
over your functions and ensure they are following expected behavior in a range
of practical scenarios.

- [Jest Documentation](https://jestjs.io/docs/getting-started)

[^1]:
    Zunino, A., Velázquez, G., Celemín, J., Mateos, C., Hirsch, M., & Rodriguez,
    J. (2020). Evaluating the performance of three popular web mapping
    libraries: A case study using Argentina’s life quality index. ISPRS
    International Journal of Geo-Information, 9(10), 563.
    <https://doi.org/10.3390/ijgi9100563>
