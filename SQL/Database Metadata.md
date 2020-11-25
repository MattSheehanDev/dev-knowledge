Database Metadata
===============================

Query all databases on server
```
USE master

select * FROM sys.databases
```

Query storage space used and max storage space available
```
SELECT
    DB_NAME() AS DbName,
    name AS FileName,
    type_desc,
    (cast(size as float) * 8) / 1024 / 1024 AS CurrentSizeGB,
    ((cast(size as float) * 8) / 1024 / 1024) - ((CAST(FILEPROPERTY(name, 'SpaceUsed') AS float) * 8) / 1024 / 1024) AS FreeSpaceGB,
    (cast(max_size as float) * 8) / 1024 / 1024 AS MaxSizeGB
FROM sys.database_files
WHERE type IN (0,1);
```

