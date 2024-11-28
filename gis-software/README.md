---
output-file: index.html
title: GIS Software
---

The ecosystem of GIS software is quite large and complex, with new software
being developed everyday. This page focuses on applications that integrate
multiple pieces of GIS software to create a single desktop or server
application. Resources for other GIS software, including spatial databases can
be found [here](https://ubc-geography.github.io/computing-resources/databases/),
while resources for geospatial libraries/packages can be found with their
associated programming languages.

- _Practical GIS_ : [UBC Library](https://go.exlibris.link/0SQNwYkl) |
  [WorldCat](https://search.worldcat.org/title/990474114)

- _GIS Fundamentals_ : [UBC Library](https://go.exlibris.link/K2SdsWd1) |
  [WorldCat](https://search.worldcat.org/title/894363293)

- _GIS: An Introduction to Mapping Technologies_ :
  [UBC Library](https://go.exlibris.link/XDzhC2Pd) |
  [WorldCat](https://search.worldcat.org/title/1376196388)

## ArcGIS Pro

Developed by Esri, ArcGIS Pro succeeded ArcMap and as the foundation to Esri's
extraordinarily popular ecosystem of GIS software. It is by far the most popular
and commonly used commercial GIS desktop application.

All UBC Students can access ArcGIS Pro through the UBC Library labs documented
in their [GIS research guide](https://guides.library.ubc.ca/gis/labs). Students,
who are enrolled in a geography course that requires access to ArcGIS Pro, will
also have access to the
[Geography Computer Labs](https://geog.ubc.ca/undergraduate/study-resources/).
Additionally, students may purchase a discounted one-year license for using
ArcGIS Pro on their personal computers from the
[UBC GIS Software page](https://gis.ubc.ca/software/).

UBC Geography maintains a department license for all ArcGIS software, which is
available to all faculty, staff, and researchers.

ArcGIS Pro is developed exclusively around Windows, so running it on a Mac or
Linux device requires either the ability to dual boot into a Windows operating
system or access to Windows from a virtual environment. Esri provides these
[instructions](https://pro.arcgis.com/en/pro-app/latest/get-started/run-pro-on-a-mac.htm)
for Mac users.

- [UBC Library Research Commons - Understanding Map Projections](https://ubc-library-rc.github.io/map-projections/)

- _ArcGIS Pro 3.x Cookbook_ :
  [UBC Library](https://learning.oreilly.com/library/view/arcgis-pro-3-x/9781837631704/)
  | [WorldCat](https://search.worldcat.org/title/1433677619)

- _Learning ArcGIS Pro 2_ : [UBC Library](https://go.exlibris.link/GQq35Gf6) |
  [WorldCat](https://search.worldcat.org/title/1181841303)

- _Computational Methods and GIS Applications in Social Science_ :
  [UBC Library](https://go.exlibris.link/YM3Mt98G) |
  [WorldCat](https://search.worldcat.org/title/1394119309)

## QGIS

QGIS is a free and open-source GIS desktop application with broad support for
Windows, Mac, and Linux operating systems. Its development is supported by the
Open Source Geospatial Foundation (OSGeo), which also supports other popular
geospatial software, like GDAL, GEOS, GrassGIS, PostGIS, and many others. You
can download and install QGIS from their
[download page](https://qgis.org/en/site/forusers/download.html) or, if you are
a UBC Vancouver student, you can access it from one of the labs listed in
[UBC Library's GIS Research Guide](https://guides.library.ubc.ca/gis/labs).

The UBC Library Research Commons frequently provides introductory workshops on
QGIS for students, faculty, and staff. You can review previous workshop
materials below and find upcoming workshops on their
[calendar](https://libcal.library.ubc.ca/calendar/vancouver?t=g&q=qgis).

- [UBC Library Research Commons - Map Production with QGIS](https://ubc-library-rc.github.io/gis-intro-qgis/)

- [UBC Library Research Commons - Network Analysis with QGIS](https://ubc-library-rc.github.io/qgis-walkability/)

- _QGIS Quick Start Guide_ : [UBC Library](https://go.exlibris.link/vXrWwwJ9) |
  [WorldCat](https://search.worldcat.org/title/1085230540)

- _Learn QGIS_ : [UBC Library](https://go.exlibris.link/yGfccBXv) |
  [WorldCat](https://search.worldcat.org/title/1085904869)

- _QGIS: Becoming a GIS Power User_ :
  [UBC Library](https://go.exlibris.link/NcZblRWv) |
  [WorldCat](https://search.worldcat.org/title/979891998)

## GeoServer

GIS servers, like ArcGIS Server, QGIS Server, and GeoServer, enable users to
publish and share their maps and geospatial data through web-hosted services.
Similar to QGIS, GeoServer has been supported as an OSGeo project. It supports
the following standard protocols: Web Feature Service (WFS), Web Map Service
(WMS), and Web Coverage Service (WCS) alongside Web Processing Service (WPS) and
Web Map Tile Service (WMTS) via added extensions. It also provides the back-end
for the geospatial content management system, GeoNode.

While GeoServer can be hosted on a virtual machine through the
[Alliance Cloud](https://ubc-geography.github.io/computing-resources/cloud-computing/#digital-research-alliance-dra),
we strongly recommend that you review and consider deploying
[cloud-optimized geospatial formats](https://guide.cloudnativegeo.org/) with
[object storage](https://ubc-geography.github.io/computing-resources/cloud-computing/object-storage.html)
as an alternative if your use case allows it.

- _GeoServer Beginner's Guide_ :
  [UBC Library](https://go.exlibris.link/ZSQc0jdm) |
  [WorldCat](https://search.worldcat.org/title/1011595394)

- _Expert GeoServer_ : [UBC Library](https://go.exlibris.link/VZSrV1cw) |
  [WorldCat](https://search.worldcat.org/title/1050170484)

## Web Mapping

Web maps, like OpenStreetMap and Google Maps, provide one of the most effective
methods for sharing geospatial data, as they enable users to render, view, and
interact with that data directly through their web browsers either via a laptop,
desktop, or mobile device without the need to install specialized GIS software.

Examples:

- [Wayfinding at UBC](https://maps.ubc.ca/)

- [City of Vancouver - VanMap](https://maps.vancouver.ca/vanmap-viewer/)

- [Government of BC - BC's Map Hub](https://governmentofbc.maps.arcgis.com/home/gallery.html)

- [bikemaps.org](https://bikemaps.org/)
-
- [walkrollmap.org](https://walkrollmap.org/)

There are a large variety of tools that can assist in developing and
distributing web maps. Prior to selecting a tool, be sure to closely analyze
your use case and assess whether the tools you are reaching for can best
addresses it. For particularly unique use cases, it may be necessary to develop
a web map from the ground up using HTML, CSS, and JavaScript. You can find a few
resources to assist that work in this site's
[JavaScript page](https://ubc-geography.github.io/computing-resources/javascript/#web-mapping).

### ArcGIS Online

Industry and government GIS experts, frequently rely on ESRI's ArcGIS Online to
provide access to their geospatial data via an extraordinarily powerful web
mapping interface. Similar to ArcGIS Pro, UBC students and researchers can learn
more about getting access to an ArcGIS Online account on the
[UBC GIS Software page](https://gis.ubc.ca/software/).

- [ESRI - ArcGIS Online - Resources](https://www.esri.com/en-us/arcgis/products/arcgis-online/resources)

An important item to note when assessing this tool for your use cases is that
your web map cannot be exported from ArcGIS Online, which means the lifespan of
your map will be heavily dependent on ESRI's servers and your continued
subscription to an ArcGIS Online account. If your web map will need to be
supported and/or preserved well into the future, consider reviewing a few
alternative options. Additionally, while the extensive number of features
included in ArcGIS web maps can make them extraordinarily powerful, those same
features can also make your map quite bloated, so if you are developing a web
map to serve communities where internet access may be limited, consider working
with a lighter web mapping tool that can be optimized to load more efficiently.

Alternatives to ArcGIS Online that may fit similar use cases include:
[Mapbox](https://www.mapbox.com/) and [CARTO](https://carto.com/), which both
run popular Software as a Service (SaaS) models for developing and hosting web
maps.

### uMap

Built on OpenStreetMap and open-source software, uMap provides a lighter, but
less feature-rich alternative to ArcGIS Online. Public instances are available,
which enable users to create and share their web maps for free. If you hope to
embed images or other media on your map, checkout the
[Object Storage page](https://ubc-geography.github.io/computing-resources/cloud-computing/object-storage.html)
for free/low-cost hosting options.

- [OSM Wiki- uMap](https://wiki.openstreetmap.org/wiki/UMap)

### QGIS2WEB

Distributed as a QGIS plugin, this tool enables users to generate web maps as
static web sites. HTML, CSS, and JavaScript are exported alongside your data,
which can then be hosted like any other static website through
[object storage](https://ubc-geography.github.io/computing-resources/cloud-computing/object-storage.html)
or providers like GitHub Pages.

- [qgis2web Wiki](https://qgis2web.github.io/qgis2web/)

### GeoNode

As noted earlier, GeoNode provides an open-source content management system atop
a GeoServer instance, which works well for developing, collaborating, and
sharing web maps. Unlike ArcGIS Online and uMap, GeoNode is only available via a
self-hosted instance, so requesting a cloud-based virtual machine would be
required to setup a server.

- [GeoNode Documentation](https://docs.geonode.org/en/master/)

### Ushahidi

Developed with a specific focus on creating web maps from crowdsourced data,
Ushahidi provides a friendly user interface for quickly creating and
distributing forms from which data can be collected and then mapped
automatically. Ushahidi can either be self-hosted or managed via a SaaS account,
but registering users should be avoided or discouraged in order to avoid
collecting any personal identifiable information (PII), which could violate UBC
policies and BC privacy regulations.

- [Ushahidi User Manual](https://docs.ushahidi.com/platform-user-manual)
