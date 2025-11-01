## 8. How it’s used in real life

- **Dev teams**: nightly `pg_dump` of production → stored in S3.
    
- **CI/CD pipelines**: restore a dump into test DB for regression testing.
    
- **Data analysts**: use logical dumps for snapshot analysis offline.
    
- **DB admins**: take `pg_basebackup` weekly + continuous WAL archiving for full disaster recovery.