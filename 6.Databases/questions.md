1. what is data directory? is where all of the files are stored? what data is there? the db which is files and what else? the server?
2. how does the logical backup work? like its a scrip but how does it store the data inside the databases?? where does it hold it?
3. what is wal? what is data file inside the db? can u make like an introduction to explain some terms related to databases i seem to be lacking some base knoledge. 
4. so a cluster is multiple databases? 
5. how do roles work in database? in postgres? in general?
6. why do i need o allow replication connection on beta? qhat does that even mean/???
7. whart does this mean??? wal_level = replica
	max_wal_senders = 5
8.  


9. cum adica before they hit tableS??? Write-Ahead Log (WAL) files — all recent changes before they hit tables
10.  ce inseamna asta: - It queries the system catalogs (like `pg_class`, `pg_attribute`) to learn the schema (tables, views, etc.).
11. how the pgdump ACTUALLY WORK? in details?
12. i dint get this line and what its used for an fits ontext host    replication    replicator    192.168.1.10/32    scram-sha-256
13. `psql` protocol
14. - Extracts actual table data using internal `COPY` commands. -??? WHERE DOES IT GET THE TABLE DATA FROM??? it it only has the files from system catalogues


15. - This snapshot “freezes” what `pg_dump` sees so your dump isn’t affected by concurrent writes.wdym? so when u make a logical  backup, you stop and freeze the database. then u take the metadata and the . what is worker session/?? - If you use `-j` (parallel dump), it “exports” that snapshot and all worker sessions reuse it so every table sees **the same point in time**. how does it take the data from the databases? alsoo if u make this logical backup u basiclaly need to run a command, the backups gets done. and then u store it and if u need it, you run it? and how often do u make it? how is it used in real life? what ab phisical? the output is just a .sql file right??



16. whoo??? - That snapshot is **exported** so that all 4 worker sessions reuse it. what is that? i think i basically need a big lesson ab this bcs i feel i have a ot of gaps 
17. explain this: PostgreSQL uses **MVCC (Multi-Version Concurrency Control)**.  
That means every transaction sees a _consistent snapshot_ of data — even while others are writing.
18. When `pg_dump` starts, it: Begins a transaction. u never told me what a transacion is\
19. - That snapshot is **exported** so that all 4 worker sessions reuse it. u never explained what worker session is
20. what does "dump" mean? - Each worker dumps different tables simultaneously — but all using the _same point in time_.
21. u never explained what a dump file is or other important terms like that
22. whata are (cron jobs