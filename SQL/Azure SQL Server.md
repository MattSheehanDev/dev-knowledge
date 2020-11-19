Azure SQL Server
===============================

Query elastic pool(s) info
```
SELECT * FROM sys.database_service_objectives
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

