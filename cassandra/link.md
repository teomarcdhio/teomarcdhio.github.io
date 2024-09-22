---
layout: default
title: Cassandra in folder links
parent: Cassandra in folder
nav_order: 1
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
