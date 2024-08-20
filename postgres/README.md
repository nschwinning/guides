## Performance Monitoring

```sh
CREATE EXTENSION pg_stat_statements;
```

## Useful Queries

Get all locks

```sql
SELECT * FROM pg_locks WHERE relation = 'trade_management_db.public.disaggregated_volume_ts'::regclass;
```

```sql
SELECT a.locktype, a.relation::regclass, a.pid, a.mode, a.granted,
       block_activity.query AS blocking_query, wait_activity.query AS waiting_query
FROM pg_locks a
JOIN pg_stat_activity block_activity ON block_activity.pid = a.pid
JOIN pg_stat_activity wait_activity ON wait_activity.pid = a.pid
WHERE NOT a.granted AND a.relation::regclass = 'trade_management_db.public.disaggregated_volume_ts'::regclass;
```
