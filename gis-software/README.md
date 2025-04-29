---
output-file: index.html
title: GIS Software
# change to date to last-modified after next modification
date: 2024-12-11
---

The ecosystem of GIS software is quite large and complex, with new software
being developed everyday. This page focuses on applications that integrate
multiple pieces of GIS software to create a single desktop or server
application. Resources for other GIS software, including spatial databases can
be found
[here](https://ubc-geography.github.io/computing-resources/databases/){target="\_blank"},
while resources for geospatial libraries/packages can be found with their
associated programming languages.

- _Practical GIS_ :
  [UBC Library](https://go.exlibris.link/0SQNwYkl){target="\_blank"} |
  [WorldCat](https://search.worldcat.org/title/990474114){target="\_blank"}

- _GIS Fundamentals_ :
  [UBC Library](https://go.exlibris.link/K2SdsWd1){target="\_blank"} |
  [WorldCat](https://search.worldcat.org/title/894363293){target="\_blank"}

- _GIS: An Introduction to Mapping Technologies_ :
  [UBC Library](https://go.exlibris.link/XDzhC2Pd){target="\_blank"} |
  [WorldCat](https://search.worldcat.org/title/1376196388){target="\_blank"}

## ArcGIS Pro

Developed by Esri, ArcGIS Pro succeeded ArcMap and as the foundation to Esri's
extraordinarily popular ecosystem of GIS software. It is by far the most popular
and commonly used commercial GIS desktop application.

All UBC Students can access ArcGIS Pro through the UBC Library labs documented
in their
[GIS research guide](https://guides.library.ubc.ca/gis/labs){target="\_blank"}.
Students, who are enrolled in a geography course that requires access to ArcGIS
Pro, will also have access to the
[Geography Computer Labs](https://geog.ubc.ca/undergraduate/study-resources/){target="\_blank"}.
Additionally, students may purchase a discounted one-year license for using
ArcGIS Pro on their personal computers from the
[UBC GIS Software page](https://gis.ubc.ca/software/){target="\_blank"}.

UBC Geography maintains a department license for all ArcGIS software, which is
available to all faculty, staff, and researchers.

ArcGIS Pro is developed exclusively around Windows, so running it on a Mac or
Linux device requires either the ability to dual boot into a Windows operating
system or access to Windows from a virtual environment. Esri provides these
[instructions](https://pro.arcgis.com/en/pro-app/latest/get-started/run-pro-on-a-mac.htm){target="\_blank"}
for Mac users.

- [UBC Library Research Commons - Understanding Map Projections](https://ubc-library-rc.github.io/map-projections/){target="\_blank"}

- _ArcGIS Pro 3.x Cookbook_ :
  [UBC Library](https://go.exlibris.link/DDP9g1WW){target="\_blank"} |
  [WorldCat](https://search.worldcat.org/title/1433677619){target="\_blank"}

- _Learning ArcGIS Pro 2_ :
  [UBC Library](https://go.exlibris.link/GQq35Gf6){target="\_blank"} |
  [WorldCat](https://search.worldcat.org/title/1181841303){target="\_blank"}

- _Computational Methods and GIS Applications in Social Science_ :
  [UBC Library](https://go.exlibris.link/YM3Mt98G){target="\_blank"} |
  [WorldCat](https://search.worldcat.org/title/1394119309){target="\_blank"}

## QGIS

QGIS is a free and open-source GIS desktop application with broad support for
Windows, Mac, and Linux operating systems. Its development is supported by the
Open Source Geospatial Foundation (OSGeo), which also supports other popular
geospatial software, like GDAL, GEOS, GrassGIS, PostGIS, and many others. You
can download and install QGIS from their
[download page](https://qgis.org/en/site/forusers/download.html){target="\_blank"}
or, if you are a UBC Vancouver student, you can access it from one of the labs
listed in
[UBC Library's GIS Research Guide](https://guides.library.ubc.ca/gis/labs){target="\_blank"}.

The UBC Library Research Commons frequently provides introductory workshops on
QGIS for students, faculty, and staff. You can review previous workshop
materials below and find upcoming workshops on their
[calendar](https://libcal.library.ubc.ca/calendar/vancouver?t=g&q=qgis){target="\_blank"}.

- [UBC Library Research Commons - Map Production with QGIS](https://ubc-library-rc.github.io/gis-intro-qgis/){target="\_blank"}

- [UBC Library Research Commons - Network Analysis with QGIS](https://ubc-library-rc.github.io/qgis-walkability/){target="\_blank"}

- _QGIS Quick Start Guide_ :
  [UBC Library](https://go.exlibris.link/vXrWwwJ9){target="\_blank"} |
  [WorldCat](https://search.worldcat.org/title/1085230540){target="\_blank"}

- _Learn QGIS_ :
  [UBC Library](https://go.exlibris.link/yGfccBXv){target="\_blank"} |
  [WorldCat](https://search.worldcat.org/title/1085904869){target="\_blank"}

- _QGIS: Becoming a GIS Power User_ :
  [UBC Library](https://go.exlibris.link/NcZblRWv){target="\_blank"} |
  [WorldCat](https://search.worldcat.org/title/979891998){target="\_blank"}

## GeoServer

GIS servers, like ArcGIS Server, QGIS Server, and GeoServer, enable users to
publish and share their maps and geospatial data through web-hosted services.
Similar to QGIS, GeoServer has been supported as an OSGeo project. It supports
the following standard protocols: Web Feature Service (WFS), Web Map Service
(WMS), and Web Coverage Service (WCS) alongside Web Processing Service (WPS) and
Web Map Tile Service (WMTS) via added extensions. It also provides the back-end
for the geospatial content management system, GeoNode.

While GeoServer can be hosted on a virtual machine through the
[Alliance Cloud](https://ubc-geography.github.io/computing-resources/cloud-computing/#digital-research-alliance-dra){target="\_blank"},
we strongly recommend that you review and consider deploying
[cloud-optimized geospatial formats](https://guide.cloudnativegeo.org/){target="\_blank"}
with
[object storage](https://ubc-geography.github.io/computing-resources/cloud-computing/object-storage.html){target="\_blank"}
as an alternative if your use case allows it.

- _GeoServer Beginner's Guide_ :
  [UBC Library](https://go.exlibris.link/ZSQc0jdm){target="\_blank"} |
  [WorldCat](https://search.worldcat.org/title/1011595394){target="\_blank"}

- _Expert GeoServer_ :
  [UBC Library](https://go.exlibris.link/VZSrV1cw){target="\_blank"} |
  [WorldCat](https://search.worldcat.org/title/1050170484){target="\_blank"}

## Web Mapping

Web maps, like OpenStreetMap and Google Maps, provide one of the most effective
methods for sharing geospatial data, as they enable users to render, view, and
interact with that data directly through their web browsers either via a laptop,
desktop, or mobile device without the need to install specialized GIS software.

Examples:

- [Wayfinding at UBC](https://maps.ubc.ca/){target="\_blank"}

- [City of Vancouver - VanMap](https://maps.vancouver.ca/vanmap-viewer/){target="\_blank"}

- [Government of BC - BC's Map Hub](https://governmentofbc.maps.arcgis.com/home/gallery.html){target="\_blank"}

- [bikemaps.org](https://bikemaps.org/){target="\_blank"}

- [walkrollmap.org](https://walkrollmap.org/){target="\_blank"}

There are a large variety of tools that can assist in developing and
distributing web maps. Prior to selecting a tool, be sure to closely analyze
your use case and assess whether the tools you are reaching for can best
addresses it. For particularly unique use cases, it may be necessary to develop
a web map from the ground up using HTML, CSS, and JavaScript. You can find a few
resources to assist that work in this site's
[JavaScript page](https://ubc-geography.github.io/computing-resources/javascript/#web-mapping){target="\_blank"}.

### ArcGIS Online

Industry and government GIS experts, frequently rely on ESRI's ArcGIS Online to
provide access to their geospatial data via an extraordinarily powerful web
mapping interface. Similar to ArcGIS Pro, UBC students and researchers can learn
more about getting access to an ArcGIS Online account on the
[UBC GIS Software page](https://gis.ubc.ca/software/){target="\_blank"}.

- [ESRI - ArcGIS Online - Resources](https://www.esri.com/en-us/arcgis/products/arcgis-online/resources){target="\_blank"}

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
[Mapbox](https://www.mapbox.com/){target="\_blank"} and
[CARTO](https://carto.com/){target="\_blank"}, which both run popular Software
as a Service (SaaS) models for developing and hosting web maps.

### uMap

Built on OpenStreetMap and open-source software, uMap provides a lighter, but
less feature-rich alternative to ArcGIS Online. Public instances are available,
which enable users to create and share their web maps for free. If you hope to
embed images or other media on your map, checkout the
[Object Storage page](https://ubc-geography.github.io/computing-resources/cloud-computing/object-storage.html){target="\_blank"}
for free/low-cost hosting options.

- [OSM Wiki- uMap](https://wiki.openstreetmap.org/wiki/UMap){target="\_blank"}

- [Deploying uMap on the Alliance Cloud](https://ubc-geography.github.io/computing-resources/cloud-computing/deploying-umap.html){target="\_blank"}

### QGIS2WEB

Distributed as a QGIS plugin, this tool enables users to generate web maps as
static web sites. HTML, CSS, and JavaScript are exported alongside your data,
which can then be hosted like any other static website through
[object storage](https://ubc-geography.github.io/computing-resources/cloud-computing/object-storage.html){target="\_blank"}
or providers like GitHub Pages.

- [qgis2web Wiki](https://qgis2web.github.io/qgis2web/){target="\_blank"}

### GeoNode

As noted earlier, GeoNode provides an open-source content management system atop
a GeoServer instance, which works well for developing, collaborating, and
sharing web maps. Unlike ArcGIS Online and uMap, GeoNode is only available via a
self-hosted instance, so requesting a cloud-based virtual machine would be
required to setup a server.

- [GeoNode Documentation](https://docs.geonode.org/en/master/){target="\_blank"}

### Ushahidi

Developed with a specific focus on creating web maps from crowdsourced data,
Ushahidi provides a friendly user interface for quickly creating and
distributing forms from which data can be collected and then mapped
automatically. Ushahidi can either be self-hosted or managed via a SaaS account,
but registering users should be avoided or discouraged in order to avoid
collecting any personal identifiable information (PII), which could violate UBC
policies and BC privacy regulations.

- [Ushahidi User Manual](https://docs.ushahidi.com/platform-user-manual){target="\_blank"}
