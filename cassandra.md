---
layout: default
title: Cassandra
nav_order: 9
has_children: true
---
### Cassandra

Install cassandra on Macos   
```brew install cassandra```   
Install cassandra with tarball or using apt install  
```https://cassandra.apache.org/doc/latest/cassandra/getting_started/installing.html```   
Modify the conf/cassandra.yaml file to allow an exteranl server ( such as janusgraph ) to interact with the cassandra datastore; set the following to the server private or public ip addresses ( dependign on the deploymnet )
```
- seeds: "10.0.4.76:7000"
listen_address: 10.0.4.76
broadcast_address: 10.0.4.76
rpc_address: 10.0.4.76
broadcast_rpc_address: 10.0.4.76
```   
Start the server   
```bin/cassandra```   
Check status of cassandra server       
```bin/nodetools status``` 

#### Links   
  
How to install cassandra [link](https://cassandra.apache.org/doc/latest/cassandra/getting_started/installing.html)  
Cheatsheet [link](https://www.baeldung.com/cassandra-query-cheat-sheet)   
