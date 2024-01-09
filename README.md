# CH_Cluster_Template

8 ClickHouse instances leveraging 3 dedicated ClickHouse Keepers

4 Shards with replication:

- across clickhouse-01 and clickhouse-03 for shard 01
- across clickhouse-02 and clickhouse-04 for shard 02

- across clickhouse-05 and clickhouse-07 for shard 03
- across clickhouse-06 and clickhouse-08 for shard 04

-- Ch Nodes

1 2
3 4

---

5 6
7 8

-- Shards & Replica

01 02 01 02
01 01 02 02

---

03 04 03 04
03 03 04 04

By default the version of ClickHouse used will be `latest`, and ClickHouse Keeper
will be `latest-alpine`. You can specify specific versions by setting environment
variables before running `docker compose up`.

```bash
export CHVER=23.4
export CHKVER=23.4-alpine
docker compose up
```

This Docker compose file deploys a configuration very similar to [these two
examples in the documentation](https://clickhouse.com/docs/en/architecture/introduction).
See the docs for information on terminology, configuration, and testing.
