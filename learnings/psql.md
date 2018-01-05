---
  PostgresSQL
---

* Administration Tools
  - psql: a command-line interface for running queries. import and export command for delimited files (CSV or tab), and a minimalistic report writer that can generate HTML output.
  - pgAdmin: a widely used free GUI tool for PostgreSQL.
  - phpPgAdmin: a free, web-based administration tool patterned after the popular phpPgMyAdmin from phpMyAdmin.
  - Adminer: a lightweight, open source PHP application with options for PostgreSQL, MySQL, SQLite, SQL Server, and Oracle, all delivered through a single interface.
* Important Database Objects
  - service: deamon of server
  - database: Each PostgreSQL service houses many individual databases.
  - schema: each database has one or more schemas
  - catalog: system schemas that store PostgreSQL built-in functions and meta-data. Each database is born containing two catalogs: **pg_catalog**, which has all the functions, tables, system views, casts, and types packaged with PostgreSQL; and **information_schema**, which consists of ANSI standard views that expose PostgreSQL metainformation in a format dictated by the ANSI SQL standard.
  - extension:  allows developers to package functions, data types, casts, custom index types, tables, GUCs(Grand Unified Configuration), etc.
  - table: tables are first of all citizens of their respective schemas, before being citizens of the database.
  - foreign table: virtual tables linked to data outside a PostgreSQL database, FDWs(foreign data wrappers) contain the magic handshake between PostgreSQL and external data sources.
  - tablespace: physical location where data is stored.
  - view: for abstracting queries and allow for updating data via a view.
  - data type: PostgreSQL has something called a composite type, which is a type that has attributes from other types.
  - cast: prescriptions for converting from one data type to another.
  - trigger: triggers detect data-change events.
  - rule: instructions to substitute one action for another.
* 
