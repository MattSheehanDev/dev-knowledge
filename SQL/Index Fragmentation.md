Index Fragmentation
====================

Average fragmentation for each table
```
DECLARE @db_id INT = DB_ID(N'name_of_database');


-- Find avg index fragmentation for single db table
SELECT
    DB_NAME(pstats.database_id) as DbName,
    pstats.object_id,
    OBJECT_SCHEMA_NAME(pstats.object_id) as SchemaName,
    OBJECT_NAME(pstats.object_id) AS TableName,
    pstats.index_id,
    idx.name AS IndexName,
    pstats.avg_fragmentation_in_percent,
    pstats.fragment_count,
    pstats.avg_fragment_size_in_pages,
    pstats.page_count
FROM sys.dm_db_index_physical_stats (@db_id, NULL, NULL, NULL, NULL) AS pstats

INNER JOIN sys.indexes AS idx ON pstats.object_id = idx.object_id AND pstats.index_id = idx.index_id

ORDER BY pstats.avg_fragmentation_in_percent DESC;

```

Average fragmentation fora  specific table
```
DECLARE @db_id INT = DB_ID(N'name_of_database');
DECLARE @table_id INT = OBJECT_ID(N'name_of_database.schema.table');



-- Find avg index fragmentation for single db table
SELECT
    DB_NAME(pstats.database_id) as DbName,
    pstats.object_id,
    OBJECT_SCHEMA_NAME(pstats.object_id) as SchemaName,
    OBJECT_NAME(pstats.object_id) AS TableName,
    pstats.index_id,
    idx.name AS IndexName,
    pstats.avg_fragmentation_in_percent,
    pstats.fragment_count,
    pstats.avg_fragment_size_in_pages,
    pstats.page_count
FROM sys.dm_db_index_physical_stats (@db_id, @table_id, NULL, NULL, NULL) AS pstats

INNER JOIN sys.indexes AS idx ON pstats.object_id = idx.object_id AND pstats.index_id = idx.index_id

ORDER BY pstats.avg_fragmentation_in_percent DESC;

```

Re-organize all indexes on a table
- Re-organize is usually sufficient and quicker than re-building unless the the fragmentation is severe.
```
ALTER INDEX ALL ON [schema].[table] REORGANIZE;
```

Re-build all indexes on a table
- `(ONLINE = ON)` rebuilds the table indexes without taking the table offline and locking access.
```
ALTER INDEX ALL ON [schema].[table] REBUILD WITH (ONLINE = ON);
```