---
layout: default
title: Cassandra in folder
has_children: true
parent: Cassandra
nav_order: 99
---

Connect to a cassandra instance  
```bash
cqlsh <IPADDRESS> 9042 -u <USERNAME> -p <PASSWORD>
```  
Show all keyspaces  
```cqlsh
DESC keyspaces;
```
Show keyspaces with select statement  
```cqlsh
SELECT * FROM system_schema.keyspaces;
```  
Use a keyspace  
```cqlsh
use janusgraph;
```  
Show edges fro the janusgraph keyspace  
```cqlsh
select * from edgestore;
```
