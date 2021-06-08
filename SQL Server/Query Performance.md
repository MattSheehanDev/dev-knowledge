Query Performance
=========================================================

1. View expensive queries (CPU Time)
```
--Expensive queries (CPU Time)
SELECT TOP 10 creation_time, 
              last_execution_time, 
              total_worker_time, 
              total_elapsed_time, 
              SUBSTRING(st.text, qs.statement_start_offset / 2 + 1, (CASE statement_end_offset
                                                                         WHEN-1
                                                                         THEN DATALENGTH(st.text)
                                                                         ELSE qs.statement_end_offset
                                                                     END - qs.statement_start_offset) / 2 + 1) AS statement_text
FROM sys.dm_exec_query_stats AS qs
     CROSS APPLY sys.dm_exec_sql_text(qs.sql_handle) AS st
ORDER BY total_worker_time DESC;

```

2. View queries with high query plan execution recompilations
    - Queries with high re-compiles can degrade CPU pressure and degrades performance
```
--High recompiles
SELECT plan_generation_num, 
       execution_count, 
       SUBSTRING(st.text, qs.statement_start_offset / 2 + 1, (CASE statement_end_offset
                                                                  WHEN-1
                                                                  THEN DATALENGTH(st.text)
                                                                  ELSE qs.statement_end_offset
                                                              END - qs.statement_start_offset) / 2 + 1) AS statement_text
FROM sys.dm_exec_query_stats AS qs
     CROSS APPLY sys.dm_exec_sql_text(qs.sql_handle) AS st
WHERE plan_generation_num > 1
ORDER BY plan_generation_num DESC;
```

3. View waiting tasks
```
-- View waiting tasks
SELECT
    st.text AS [SQL Text],
    c.connection_id,
    w.session_id,
    w.wait_duration_ms,
    w.wait_type,
    w.resource_address, 
    w.blocking_session_id,
    w.resource_description,
    c.client_net_address,
    c.connect_time
FROM sys.dm_os_waiting_tasks AS w
INNER JOIN sys.dm_exec_connections AS c ON w.session_id = c.session_id 
CROSS APPLY (SELECT * FROM sys.dm_exec_sql_text(c.most_recent_sql_handle)) AS st 
              WHERE w.session_id > 50 AND w.wait_duration_ms > 0
ORDER BY c.connection_id, w.session_id
GO
```