---
layout: default
title: Helm Commands
parent: Helm
nav_order: 1
---
### Helm commands

Produce a sample of the chart before creatign the bundle ( from within the chart folder )
```helm template . -f values.yaml > sample.yaml```
List available helm deployments inside a namesapce  
```helm list -n namesapce```
Package helm chart ( from within the chart folder )   
```helm package NAMEOFTHECHART```   
Install specific version of a chart    
```helm install my-mongodb bitnami/mongodb --version 8.3.1```   
Find a chart   
```helm search repo mongo -l```  
Check status of a chart   
```helm status <nameofthechart>```   
Debug mode to troubleshoot failed deployments   
```helm install my-mongodb bitnami/mongodb --version 8.3.1 --debug```   

  
