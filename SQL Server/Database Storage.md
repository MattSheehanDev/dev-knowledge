Database Storage
===============================

1. Query storage space used and max storage space available
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

1. Query table storage size
    - Useful when trying to determine why a database storage space is so large
```
SELECT 
    s.Name AS SchemaName,
    t.NAME AS TableName,
    p.rows AS RowCounts,
    SUM(a.total_pages) * 8 AS TotalSpaceKB, 
    SUM(a.used_pages) * 8 AS UsedSpaceKB, 
    (SUM(a.total_pages) - SUM(a.used_pages)) * 8 AS UnusedSpaceKB
FROM 
    sys.tables t
INNER JOIN 
    sys.schemas s ON s.schema_id = t.schema_id
INNER JOIN      
    sys.indexes i ON t.OBJECT_ID = i.object_id
INNER JOIN 
    sys.partitions p ON i.object_id = p.OBJECT_ID AND i.index_id = p.index_id
INNER JOIN 
    sys.allocation_units a ON p.partition_id = a.container_id
WHERE 
    t.NAME NOT LIKE 'dt%'    -- filter out system tables for diagramming
    AND t.is_ms_shipped = 0
    AND i.OBJECT_ID > 255 
GROUP BY 
    t.Name, s.Name, p.Rows
ORDER BY 
    UsedSpaceKB DESC
```

