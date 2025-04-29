---
output-file: index.html
title: Databases
# change to date to last-modified after next modification
date: 2024-12-11
---

Databases, and particularly spatial databases as a piece of GIS software, play a
crucial role in storing and accessing geospatial data. Multiple relational
database management systems can be extended to support spatial databases, while
common geospatial data formats like GeoPackage and Esri's Geodatabase are
self-contained databases.

Understanding how databases and how to query them efficiently with SQL, is an
extraordinarily useful skill when working with geospatial data.

- [Software Carpentry - Databases and SQL](https://swcarpentry.github.io/sql-novice-survey/){target="\_blank"}

- [How to create and access MySQL and PostgreSQL databases on DRI systems - Video](https://youtu.be/3uHSXXQwJpQ){target="\_blank"}

- _Geospatial Analysis with SQL_ :
  [UBC Library](https://go.exlibris.link/N6ybsHyL){target="\_blank"} |
  [WorldCat](https://search.worldcat.org/title/1356796776){target="\_blank"}

- _Practical SQL_ :
  [UBC Library](https://go.exlibris.link/KT2RjyVN){target="\_blank"} |
  [WorldCat](https://search.worldcat.org/title/1291870871){target="\_blank"}

- _SQL All-in-One for Dummies_ :
  [UBC Library](https://go.exlibris.link/s1CwKGdS){target="\_blank"} |
  [WorldCat](https://search.worldcat.org/title/1429319351){target="\_blank"}

- _Getting Started with SQL and Databases: Managing and Manipulating Data with
  SQL_ : [UBC Library](https://go.exlibris.link/8P3M1W2j){target="\_blank"} |
  [WorldCat](https://search.worldcat.org/title/1381743217){target="\_blank"}

## DuckDB

When running memory-intensive workloads, DuckDB is a powerful tool to have on
hand. Unlike many other database management systems, which focus on data
storage, DuckDB focuses on data analysis, and it includes easy installation
methods for Python, R, and JavaScript environments.

- _Getting Started with DuckDB_ :
  [UBC Library](https://go.exlibris.link/M0l5WQw5){target="\_blank"} |
  [WorldCat](https://search.worldcat.org/title/1436457021){target="\_blank"}

- _DuckDB: Up and Running_ :
  [UBC Library](https://go.exlibris.link/YFbRpYc9){target="\_blank"} |
  [WorldCat](https://search.worldcat.org/title/1442327944){target="\_blank"}

- [DuckDB Documentation](https://duckdb.org/docs/){target="\_blank"}

- [DuckDB - Spatial Extension](https://duckdb.org/docs/extensions/spatial.html){target="\_blank"}

## PostgreSQL

Due to the PostGIS extension, PostgreSQL is one of the most commonly used
database management systems for storing and accessing geospatial data. GIS
software, like GeoServer and QGIS, provide tight integrations around
PostGIS-enabled databases.

- [QGIS Manual - Database Concepts with PostgreSQL](https://docs.qgis.org/3.34/en/docs/training_manual/database_concepts/index.html){target="\_blank"}

- _Learn PostgreSQL_ :
  [UBC Library](https://go.exlibris.link/DPVZ3PFk){target="\_blank"} |
  [WorldCat](https://search.worldcat.org/title/1407633395){target="\_blank"}

- _PostgreSQL Query Optimization_ :
  [UBC Library](https://go.exlibris.link/Mp0jzFgZ){target="\_blank"} |
  [WorldCat](https://search.worldcat.org/title/1417197322){target="\_blank"}

### Hosting

While it's possible to host a PostgreSQL database on your local machine, to take
full advantage of a relational database management system, you'll want to host
the database on its own server. The Digital Research Alliance provides free
database hosting for researchers based in Canada through their cloud computing
services, and alternatively, many commercial cloud computing and
software-as-a-service providers include specialized services for hosting
databases.

#### Alliance

- [Database Servers -- Cedar PostgreSQL](https://docs.alliancecan.ca/wiki/Database_servers#Cedar_PostgreSQL_server){target="\_blank"}

- [WestDRI - How to create and access MySQL and PostgreSQL databases on DRI systems](https://training.westdri.ca/tools/rdm/#how-to-create-and-access-mysql-and-postgresql-databases-on-dri-systems){target="\_blank"}

#### Cloud / SaaS Providers

- [Microsoft Azure](https://azure.microsoft.com/en-ca/products/postgresql/){target="\_blank"}

- [AWS](https://aws.amazon.com/rds/postgresql/){target="\_blank"}

- [Google Cloud](https://cloud.google.com/sql/docs/postgres){target="\_blank"}

- [Supabase](https://supabase.com/docs/guides/database){target="\_blank"}

- [Railway](https://docs.railway.app/databases/postgresql){target="\_blank"}

### GIS Extensions / Libraries

- [PostGIS](https://postgis.net/documentation/){target="\_blank"}

  - [Introduction to PostGIS](https://postgis.net/workshops/postgis-intro/){target="\_blank"}

  - _PostGIS in Action_ :
    [UBC Library](https://go.exlibris.link/cKtRz8Pm){target="\_blank"} |
    [WorldCat](https://search.worldcat.org/title/1339878967){target="\_blank"}

  - _PostGIS Cookbook_ :
    [UBC Library](https://go.exlibris.link/z6HBlj5t){target="\_blank"} |
    [WorldCat](https://search.worldcat.org/title/1105805332){target="\_blank"}

  - _Mastering PostGIS_ :
    [UBC Library](https://go.exlibris.link/bCV4PRwJ){target="\_blank"} |
    [WorldCat](https://search.worldcat.org/title/991530184){target="\_blank"}

- [pgRouting](https://docs.pgrouting.org/latest/en/pgRouting-introduction.html){target="\_blank"}

## MySQL and MariaDB

While not nearly as a popular in geospatial computing as PostgreSQL, MySQL and
its closely-related fork, MariaDB, are extraordinarily popular database
management systems, which remains a fundamental building block for many
open-source web applications, like WordPress, Drupal, Omeka-S, and Scalar.

### Hosting

Similar to PostgreSQL, both the Alliance cloud and numerous commercial cloud
providers include support for hosting and managing instances of a MySQL server.

#### Alliance

- [Database Servers -- Cedar MySQL](https://docs.alliancecan.ca/wiki/Database_servers#Cedar_MySQL_server){target="\_blank"}

#### Cloud / SaaS Providers

- [Microsoft Azure](https://azure.microsoft.com/en-ca/products/mysql/){target="\_blank"}

- [AWS](https://aws.amazon.com/rds/mysql/){target="\_blank"}

- [Google Cloud](https://cloud.google.com/sql/docs/mysql){target="\_blank"}

- [PlanetScale](https://planetscale.com/docs){target="\_blank"}

- [Railway](https://docs.railway.app/databases/mysql){target="\_blank"}

### GIS Extensions / Libraries

- [MySQL Spatial](https://dev.mysql.com/doc/refman/8.0/en/spatial-analysis-functions.html){target="\_blank"}
