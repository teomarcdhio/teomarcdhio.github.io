---
layout: default
title: Cassandra in folder links
parent: Cassandra in folder
---

Connect to a cassandra instance  
```bash
cqlsh <IPADDRESS> 9042 -u <USERNAME> -p <PASSWORD>
```  
Show all keyspaces  
```sql
DESC keyspaces;
```
Show keyspaces with select statement  
```sql
SELECT * FROM system_schema.keyspaces;
```  
Use a keyspace  
```sql
use janusgraph;
```  
Show edges fro the janusgraph keyspace  
```sql
select * from edgestore;
```
