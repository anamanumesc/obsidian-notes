1. what is data directory? is where all of the files are stored? what data is there? the db which is files and what else? the server?
2. how does the logical backup work? like its a scrip but how does it store the data inside the databases?? where does it hold it?
3. what is wal? what is data file inside the db? can u make like an introduction to explain some terms related to databases i seem to be lacking some base knoledge. 
4. so a cluster is multiple databases? 
5. how do roles work in database? in postgres? in general?
6. why do i need o allow replication connection on beta? qhat does that even mean/???
7. whart does this mean??? wal_level = replica
	max_wal_senders = 5
8.  

|                                                                         |
| ----------------------------------------------------------------------- |
| Write-Ahead Log (WAL) files — all recent changes before they hit tables |


9. cum adica before they hit tableS??? Write-Ahead Log (WAL) files — all recent changes before they hit tables
10.  ce inseamna asta: - It queries the system catalogs (like `pg_class`, `pg_attribute`) to learn the schema (tables, views, etc.).
11. how the pgdump ACTUALLY WORK? in details?
