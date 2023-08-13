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
```helm package <nameofthechart>```   
Install specific version of a chart    
```helm install <nameofthechart> bitnami/mongodb --version 8.3.1```      
Find a chart    
```helm search repo mongo -l```      
Check status of a chart   
```helm status <nameofthechart>```   
View logs of chart release.   
```helm history <nameofthechart>```.     
Debug mode to troubleshoot failed deployments       
```helm install my-mongodb bitnami/mongodb --version 8.3.1 --debug```   
To list all helm deploymnets including failed or pending status    
```helm ls -a -n yournamespace```    
Show falues of a chart   
```helm show values grafana/mimir-distributed```    
Set variable against parent proprety to avoid nil reference (https://stackoverflow.com/questions/65790905/nil-pointer-evaluating-interface-when-installing-a-helm-chart )    
```
 {{- $flowable := .Values.flowable }}
            {{- if $flowable.enabled }}
            - name: "postgres.password"
              valueFrom:
                secretKeyRef:
                  name: flowable-secret
                  key: password
            {{- else }}
```  
