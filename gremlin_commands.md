---
layout: default
title: Gremlin Commands
parent: Gremlin
nav_order: 1
---
### Gremlin commands


Connect to a local janusgraph server   
```:remote connect tinkerpop.server conf/remote.yaml```    
Enable remote console        
```:remote console```    
Check connectivity to datastore         
```graph```   
Create a vertex   
```v1 = graph.addVertex(label, "person", "name", "John")```   
Retrieve data of a vertex   
```g.V().has("name", "John").valueMap()```   
Retrieve data for all vertexes   
```g.V().valueMap()```   
List all vertexes   
```g.V().toList()```
```g.V()```    





