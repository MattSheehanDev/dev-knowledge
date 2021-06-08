Database Tables
====================================

1. List all database tables
```
SELECT
    schema_name(t.schema_id) as schema_name,
    t.name as table_name,
    t.create_date,
    t.modify_date
FROM sys.tables t
ORDER BY schema_name, table_name;
```

