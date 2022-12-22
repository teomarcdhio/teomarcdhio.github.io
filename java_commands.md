---
layout: default
title: Java Commands
parent: Java
nav_order: 1
---
### Java
Check Java paramaters ( here piped to grep specific values )      
```java -XX:+PrintFlagsFinal -version | grep grep -i maxheap'```   
Check how much heap memory is allocated if using the -XX:MaxRAMPercentage sett o 50%     
```java -XX:+PrintFlagsFinal -XX:MaxRAMPercentage=50.0 -version | grep -i maxheap```
### Bazel
Build a project  
```bazel build```
Clean cache  
```bazel clean --expunge```

