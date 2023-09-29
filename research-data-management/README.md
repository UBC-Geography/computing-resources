# Research Data Management (RDM)

- [UBC Library Research Commons - Research Data Management](https://ubc-library-rc.github.io/rdm/)

- [Research Data Management Video -- Part 1](https://www.youtube.com/watch?v=TxYlHMieXAM)

- [Research Data Management Video -- Part 2](https://www.youtube.com/watch?v=q5eXXps1o04)

## Recommended GIS and Geospatial File Formats

GIS software and other geospatial computing software and packages can support a
wide array of file formats for vector and raster data thanks in large part to
the Geospatial Data Abstraction Library (GDAL). When creating, enhancing, and/or
storing geospatial data, it is important to carefully select a format that best
meets the needs of your project. The formats listed below focus on cases that
may require broad usability among various GIS platforms and software,
preservation, and performance.

Relevant resources:

- [Open Geospatial Consortium Standards](https://www.ogc.org/standard/sfs/)

- [Library of Congress - Preservation - Recommended Formats Statement - GIS, Geospatial and Non-GIS Cartographic](https://www.loc.gov/preservation/resources/rfs/geo-carto.html)

- [GDAL Vector Drivers](https://gdal.org/drivers/vector/index.html)

- [GDAL Raster Drivers](https://gdal.org/drivers/raster/index.html)

- [ArcGIS - Best Practices - Imagery Formats and Performance](https://doc.arcgis.com/en/imagery/workflows/best-practices/imagery-formats-and-performance.htm)

### Vector

#### [OGC GeoPackage](https://www.geopackage.org/)

Developed and maintained as an OGC standard, GeoPackage has become a broadly
supported format for storing and transferring GIS data. In addition to vector
data, it can also store raster data. This is the recommended and default format
for vector data in QGIS.

#### [ESRI File Geodatabase (FileGDB)](https://pro.arcgis.com/en/pro-app/latest/help/data/geodatabases/manage-file-gdb/file-geodatabases.htm)

Created by ESRI, the File Geodatabase format has been developed as an
alternative to Shapefile with the intention to overcome some of its shortcomings
and act as a possible successor.

#### [ESRI Shapefile](https://pro.arcgis.com/en/pro-app/latest/help/data/shapefiles/working-with-shapefiles-in-arcgis-pro.htm)

By far the most popular vector format, Shapefile was developed by ESRI in the
90's and has continued to be maintained by them. While the format is not fully
open, it's nevertheless found an extraordinary level of support among GIS and
other geospatial software.

#### [GeoJSON](https://geojson.org/)

GeoJSON provides a lightweight format that can be easily read and written via
JavaScript. This format is particularly well-suited for web mapping and easily
integrates with Leaflet.

#### [FlatGeobuf](https://flatgeobuf.org/)

A relatively new format that has shown significant performance improvements
compared to the formats listed above. FlatGeobuf currently lacks the backing of
standardization, but it has found broad support in geospatial packages and
software. It is also in early stages for proposal as an OGC Community standard.

#### [GeoParquet](https://geoparquet.org/)

Similar to FlatGeobuf, GeoParquet has recently seen a stable release with
significant performance improvements compared to GeoPackage and Shapefile, and
it is quickly finding support among GIS and other geospatial computing software.
This format is open-source, but has yet to reach standardization. Its developers
intend to propose it for adoption as an OGC standard.

### Raster

#### [GeoTIFF](https://www.ogc.org/standard/geotiff/) and [Cloud Optimized GeoTIFF (COG)](https://www.cogeo.org/)

GeoTIFF has become the dominant format for raster data used in GIS and other
geospatial computing due in large part to its development on open-source
standards. It's also often the default and recommended format in libraries like
GDAL and GIS software like QGIS. The format has been further improved thanks to
the development of Cloud Optimized GeoTIFFs (COG), which enhances the capacity
of GeoTIFF for cloud computing and access via the web. COG files can be stored
and easily accessed via S3 object stores, like that supported by UBC ARC
Chinook.

Built atop the TIFF file format, GeoTIFFs also support multiple compression
algorithms that can significantly reduce their overall file size. Understanding
and using these algorithms effectively can maximize computing resources while
also mitigating any data loss.

##### Uncompressed vs Lossless vs Lossy

GeoTIFFs can often be distributed without any compression at all. While the
clear drawback to this approach is extraordinarily large file sizes, there can
be benefits in ensuring that files do not need to be either encoded or decoded,
which requires varying levels of computing time and in some cases libraries that
are not supported by commonly used operating systems or software.

On the other hand, GeoTIFFs can be compressed using lossy algorithms, with the
most common being JPEG. Applying a lossy algorithm can significantly reduce
overall file sizes, but it comes with a large drawback, varying levels of data
loss. A GeoTIFF that is compressed using JPEG will always lose some data, even
if the compression quality is set to 100.

Lossless compression provides a valuable middle ground between lossy compression
and using no compression at all. A GeoTIFF that uses lossless compression can
see varying levels of file size reduction based on the raster data and
compression algorithm used. Again a single drawback is that encoding and
decoding a large lossless file can require varying amounts of computing time.
Encoding files on powerful machines can reduce encoding times while serving
files as COGs can help reduce some of the decoding time as only the needed
portions of the file will be downloaded and decoded by end users.

The Translate tool found in the GDAL library is the most commonly used tool for
creating GeoTIFFs and COGs, and it supports a broad set of
[compression algorithms](https://gdal.org/drivers/raster/cog.html#general-creation-options).
The following algorithms are important to note:

- [LZW](https://en.wikipedia.org/wiki/Lempel%E2%80%93Ziv%E2%80%93Welch) - This
  is a lossless algorithm with broad support, and it's the current default used
  by GDAL. While it can be relatively fast, this algorithm is not optimized for
  raster data, so reductions in file size may be minimal. Nevertheless, when in
  doubt, this is the algorithm to choose.

- [LERC](https://esri.github.io/lerc/) - Developed and maintained by Esri, this
  algorithm has been optimized for raster data and can support either lossy or
  lossless compression. While lacking the level of support provided by LZW or
  JPEG, this algorithm is relatively fast and provides a valuable middle ground
  between the two.

- [JPEG](https://jpeg.org/jpeg/) - Well supported and backed by solid,
  open-source standards, this has been the defacto lossy algorithm for raster
  data over the past 30 years. This a solid choice if you are looking to display
  a raster on the web and require broad support across web browsers and other
  software.

- [WEBP](https://developers.google.com/speed/webp/) - While it is well supported
  by modern web browsers, this algorithm is not developed on open-source
  standards. It supports both lossy and lossless compression. It also provides
  improved compression ratios over JPEG and currently provides the best option
  for displaying a raster on the web, but it lacks broader support in other
  software and will likely be replaced by JXL in the future.

- [JXL](https://jpeg.org/jpegxl/index.html) - This is still a relatively new
  standard that has been developed as a successor to JPEG and JPEG2000. Similar
  to LERC and WEBP, it supports both lossy and lossless compression, but it is
  capable of reaching significantly better compression ratios at the expense of
  slower encoding and decoding times. It also has yet to reach similar levels of
  support as JPEG or LZW and not all distributions of GDAL include the necessary
  library to use this algorithm, but it is well worth monitoring in the future
  as its support grows.
