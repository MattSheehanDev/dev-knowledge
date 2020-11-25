Azure SQL Server
===============================

Query elastic pool(s) info
```
SELECT * FROM sys.database_service_objectives
```

Get all elastic pools for a server
```
USE master

SELECT DISTINCT
    elastic_pool_name
FROM sys.elastic_pool_resource_stats
```

Query database and elastic pool(s) info
```
SELECT
    @@SERVERNAME as [ServerName],
    d.name as DatabaseName,
    dso.elastic_pool_name,
    dso.edition,
    dso.service_objective
FROM
    sys.databases d inner join sys.database_service_objectives dso on d.database_id = dso.database_id
WHERE d.name <> 'master'
ORDER BY
    d.name, dso.elastic_pool_name
```

Get elastic pool storage space used and max storage space available
```
SELECT TOP 1
    elastic_pool_name,
    avg_storage_percent / 100.0 * elastic_pool_storage_limit_mb AS ElasticPoolDataSpaceUsedInMB,
    elastic_pool_storage_limit_mb as ElasticPoolMaxSizeInMB,
    (avg_storage_percent / 100.0 * elastic_pool_storage_limit_mb) / elastic_pool_storage_limit_mb * 100 as ElasticPoolDataSpaceUsedPercent
FROM sys.elastic_pool_resource_stats
WHERE elastic_pool_name = 'name-of-elastic-pool'
ORDER BY end_time DESC
```


