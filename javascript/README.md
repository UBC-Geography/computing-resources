---
output-file: index.html
title: JavaScript
---

While not nearly as useful as Python or R in geospatial computing, JavaScript
can be a useful language for a geographer to have on their radar, especially if
they are interested in creating web maps and/or sharing their research online
via interactive visualizations.

## Geospatial Libraries/Packages

- [Awesome Frontend GIS](https://github.com/joewdavies/awesome-frontend-gis)

### Web Mapping

- [Awesome Geospatial -- Web Mapping](https://github.com/sacridini/Awesome-Geospatial#web-map-development)

#### Leaflet

The smallest and most popular of the three major JavaScript web mapping
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

### Visualizations

- [D3 Documentation](https://github.com/d3/d3/wiki)

- [Observable Plot Documentation](https://observablehq.com/plot/getting-started)

- [Deck.gl Documentation](https://deck.gl/docs)

### Observable JS

- [Observable Documentation](https://observablehq.com/@observablehq/documentation?collection=@observablehq/documentation)

## Formatting

Sometimes writing code can get a bit messy. Formatters can automatically
reformat your code to make it cleaner and easier to read while following a set
of standards and best practices.

- [Prettier Documentation](https://prettier.io/docs/en/index.html)

## Linting

Using a static analysis tool, or linter, is a common best practice among
programmers that helps in identifying and fixings mistakes when writing code by
ensuring that you follow the correct syntax and a guiding set of best practices.

- [ESLint Documentation](https://eslint.org/docs/latest/)

## Type Checking

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

## Testing Framework

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
