Cluster =  the top-level container that holds one or more databases.
	contains the data directory, system catalogs, configuration files, multiple databases
Database = a single, logical collection of data within that cluster that has schemas, tables, functions, users
Individual object = a table view, a function, or index


logical backup = a file, compatible with other os . inefficient in big databases
physical backup = 
object = any database content > table, index, view, function
cold backup = when postgresql is stopped. simple but causes downtime
hot backup = whrn postgres is running - needs WAL archiving 




# Logical backup (COPY command, pg_dump and pg_dumpall utilities)





---
# Physical backup

# What is physical backup (copy of data + WAL files)

pgdata = The main PostgreSQL data directory containing cluster data files.



U can only restore an entire cluster 


Cold and hot backup 
Replication protocol
Standalone backups 
Continuous archiving of WAL files