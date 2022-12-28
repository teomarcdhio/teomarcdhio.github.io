---
layout: default
title: Cassandra Commands
parent: Cassandra
nav_order: 1
---
### Cassandra commands


Connect to a cassandra instance 
```cqlsh <IPADDRESS>  9042 -u <USERNAME> -p <PASSWORD>```    
Show all keyspaces      
```DESC keyspaces;```    
Shqo keyspaces with select statement      
```SELECT * FROM system_schema.keyspaces;``` 
