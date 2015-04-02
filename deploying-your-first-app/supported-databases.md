---
title: Supported databases
---

# Supported databases

> Computers have virtually replaced tape recorders.

> — Tony Visconti


All databases supported by the Catalyze PaaS are available either in single node or highly available (HA) configurations.

Databases supported in the single node deployment are:
- Postgres
- MySQL (Percona)
- mongoDB

Support is planned for the following shortly (again to be prioritized based on customer demand)
- Couchdb - [Request Support](mailto:support@catalyze.io?subject=CouchDB support)
- SQLite - [Request Support](mailto:support@catalyze.io?subject=SQLite support)
- Cassandra - [Request Support](mailto:support@catalyze.io?subject=Cassandra support)
- HBase - [Request Support](mailto:support@catalyze.io?subject=HBase support)
- Other - [Request Support](mailto:support@catalyze.io?subject=Other DB support)

The currently supported databases are also available in HA mode which is described more below.

#### Postgres HA (in process)
Postgres HA is configured as follows:
- A pair of Postgres containers deployed as master and slave respectively
- Streaming replication is enabled between the master and slave using [WAL-E](https://github.com/wal-e/wal-e)

More details will be forthcoming shortly.

#### MySQL (Percona) HA (in process)
Percona MySQL HA is configured as follows:
- A pair of Percona MySQL containers deployed as master and slave respectively

More details will be forthcoming shortly.

#### MongoDB HA (in process)
mongoDB cluster deployments have a bunch of challenges associated with them especially when deploying in an automated fashion primarily due to the way members of a cluster need to announce themselves and the need to have their IPs and hostnames known in advance. Additionally, mongoDB requires either:
- at least 3 containers / nodes to be available for a cluster to work appropriately and avoid the "split-brain" problem
- or alternatively, employ an "arbiter" node that can manage the assignment of master or slave. This is the option we've chosen to go with.

More details will be forthcoming shortly.


HA or single node deployment options can be selected at definition / deploy time via the dashboard.


