Cluster =  the top-level container that holds one or more databases.
	contains the data directory, system catalogs, configuration files, multiple databases
Database = a single, logical collection of data within that cluster that has schemas, tables, functions, users
Individual object = a table view, a function, or index


logical backup = a file, compatible with other os . inefficient in big databases
physical backup = 
object = any database content > table, index, view, function
cold backup = when postgresql is stopped. simple but causes downtime
hot backup = whrn postgres is running - needs WAL archiving 

pgdata = The main PostgreSQL data directory containing cluster data files.
- It queries the system catalogs (like `pg_class`, `pg_attribute`) to learn the schema (tables, views, etc.).
Data files = These are the actual files that store table contents.


-----
# Logical backup (COPY command, pg_dump and pg_dumpall utilities)

## pg_dump
`pg_dump` connects to the database (just like a client).


---
# Physical backup

## WAL

They are binary logs, not human-readable.





U can only restore an entire cluster 




Cold and hot backup 
Replication protocol
Standalone backups 
Continuous archiving of WAL files