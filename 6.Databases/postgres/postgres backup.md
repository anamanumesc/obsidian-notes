
-----
# Logical backup (COPY command, pg_dump and pg_dumpall utilities)

- smaller. only one db or individual object
- reads system cataloges
- info from system catalogues
## pg_dump
`pg_dump` connects to the database (just like a client). - not the whole cluster
it takes the info from the metadata from that cluster
and it writes a .sql document and if u run it it reates a new db
if u add Fc option it gets compressed
if u add Fp u can read it

## pg_restore


---
# Physical backup
creates a snapshot of all the files the postrges uses , not only the metadata ig

## WAL

They are binary logs, not human-readable.

- These are **PostgreSQL configuration parameters** (in `postgresql.conf`).
wal_level = replica
max_wal_senders = 5
Tells PostgreSQL to write **enough detail in the WAL** to support replication and backups.
Defines how many **replication connections** can exist simultaneously.


## pg_basebackup
- has a different protocol - client
- needs wal level = replica
- server checks for this line:
- `host replication replicator 192.168.1.10/32 scram-sha-256`
- `pg_basebackup` runs as a privileged command that copies those files while the server is online.
- tar mode - archives, plain mode = directory tree
- 
how do i use it?? when?? give me life scenarios. where do u take the data from? in pg dump and in pg_basebackup




U can only restore an entire cluster 

----

Cold and hot backup 
Replication protocol
Standalone backups 
Continuous archiving of WAL files


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

### SYSTEM CATALOGUES
contain hidden system tables that describe itself
`pg_class` = One row per table, index, or sequence (their names, OIDs, etc.)
`pg_attribute` = One row per column (its name, type, order, etc.)
`pg_type` = all data types
`pg_database` = all databases in the cluster
`pg_roles` = all users/roles
