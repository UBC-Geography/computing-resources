---
output-file: index.html
title: Databases
---

Databases, and particularly spatial databases as a piece of GIS software, play a
crucial role in storing and accessing geospatial data. Multiple relational
database management systems can be extended to support spatial databases, while
common geospatial data formats like GeoPackage and Esri's Geodatabase are
self-contained databases.

Understanding how databases and how to query them efficiently with SQL, is an
extraordinarily useful skill when working with geospatial data.

- [Software Carpentry - Databases and SQL](https://swcarpentry.github.io/sql-novice-survey/)

- [How to create and access MySQL and PostgreSQL databases on DRI systems - Video](https://youtu.be/3uHSXXQwJpQ)

- _Geospatial Analysis with SQL_ :
  [UBC Library](https://go.exlibris.link/N6ybsHyL) |
  [WorldCat](https://search.worldcat.org/title/1356796776)

- _Practical SQL_ : [UBC Library](https://go.exlibris.link/KT2RjyVN) |
  [WorldCat](https://search.worldcat.org/title/1291870871)

- _SQL All-in-One for Dummies_ :
  [UBC Library](https://go.exlibris.link/s1CwKGdS) |
  [WorldCat](https://search.worldcat.org/title/1429319351)

- _Getting Started with SQL and Databases: Managing and Manipulating Data with
  SQL_ : [UBC Library](https://go.exlibris.link/8P3M1W2j) |
  [WorldCat](https://search.worldcat.org/title/1381743217)

## DuckDB

When running memory-intensive workloads, DuckDB is a powerful tool to have on
hand. Unlike many other database management systems, which focus on data
storage, DuckDB focuses on data analysis, and it includes easy installation
methods for Python, R, and JavaScript environments.

- _Getting Started with DuckDB_ :
  [UBC Library](https://learning.oreilly.com/library/view/getting-started-with/9781803241005/)
  | [WorldCat](https://search.worldcat.org/title/1436457021)

- _DuckDB: Up and Running_ : [UBC Library](https://go.exlibris.link/YFbRpYc9) |
  [WorldCat](https://search.worldcat.org/title/1442327944)

- [DuckDB Documentation](https://duckdb.org/docs/)

- [DuckDB - Spatial Extension](https://duckdb.org/docs/extensions/spatial.html)

## PostgreSQL

Due to the PostGIS extension, PostgreSQL is one of the most commonly used
database management systems for storing and accessing geospatial data. GIS
software, like GeoServer and QGIS, provide tight integrations around
PostGIS-enabled databases.

- [QGIS Manual - Database Concepts with PostgreSQL](https://docs.qgis.org/3.34/en/docs/training_manual/database_concepts/index.html)

- _Learn PostgreSQL_ : [UBC Library](https://go.exlibris.link/DPVZ3PFk) |
  [WorldCat](https://search.worldcat.org/title/1407633395)

- _PostgreSQL Query Optimization_ :
  [UBC Library](https://go.exlibris.link/Mp0jzFgZ) |
  [WorldCat](https://search.worldcat.org/title/1417197322)

### Hosting

While it's possible to host a PostgreSQL database on your local machine, to take
full advantage of a relational database management system, you'll want to host
the database on its own server. The Digital Research Alliance provides free
database hosting for researchers based in Canada through their cloud computing
services, and alternatively, many commercial cloud computing and
software-as-a-service providers include specialized services for hosting
databases.

#### Alliance

- [Database Servers -- Cedar PostgreSQL](https://docs.alliancecan.ca/wiki/Database_servers#Cedar_PostgreSQL_server)

#### Cloud / SaaS Providers

- [Microsoft Azure](https://azure.microsoft.com/en-ca/products/postgresql/)

- [AWS](https://aws.amazon.com/rds/postgresql/)

- [Google Cloud](https://cloud.google.com/sql/docs/postgres)

- [Supabase](https://supabase.com/docs/guides/database)

- [Railway](https://docs.railway.app/databases/postgresql)

### GIS Extensions / Libraries

- [PostGIS](https://postgis.net/documentation/)

  - [Introduction to PostGIS](https://postgis.net/workshops/postgis-intro/)

  - _PostGIS in Action_ : [UBC Library](https://go.exlibris.link/cKtRz8Pm) |
    [WorldCat](https://search.worldcat.org/title/1339878967)

  - _PostGIS Cookbook_ : [UBC Library](https://go.exlibris.link/z6HBlj5t) |
    [WorldCat](https://search.worldcat.org/title/1105805332)

  - _Mastering PostGIS_ : [UBC Library](https://go.exlibris.link/bCV4PRwJ) |
    [WorldCat](https://search.worldcat.org/title/991530184)

- [pgRouting](https://docs.pgrouting.org/latest/en/pgRouting-introduction.html)

## MySQL and MariaDB

While not nearly as a popular in geospatial computing as PostgreSQL, MySQL and
its closely-related fork, MariaDB, are extraordinarily popular database
management systems, which remains a fundamental building block for many
open-source web applications, like WordPress, Drupal, Omeka-S, and Scalar.

### Hosting

Similar to PostgreSQL, both the Alliance cloud and numerous commercial cloud
providers include support for hosting and managing instances of a MySQL server.

#### Alliance

- [Database Servers -- Cedar MySQL](https://docs.alliancecan.ca/wiki/Database_servers#Cedar_MySQL_server)

#### Cloud / SaaS Providers

- [Microsoft Azure](https://azure.microsoft.com/en-ca/products/mysql/)

- [AWS](https://aws.amazon.com/rds/mysql/)

- [Google Cloud](https://cloud.google.com/sql/docs/mysql)

- [PlanetScale](https://planetscale.com/docs)

- [Railway](https://docs.railway.app/databases/mysql)

### GIS Extensions / Libraries

- [MySQL Spatial](https://dev.mysql.com/doc/refman/8.0/en/spatial-analysis-functions.html)
