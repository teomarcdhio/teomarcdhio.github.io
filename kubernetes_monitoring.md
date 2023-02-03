---
layout: default
title: Kubernetes monitoring
parent: Kubernetes
nav_order: 2
---

### Kubernetes monitoring tools

Prometheus offical helm package [link](https://artifacthub.io/packages/helm/prometheus-community/prometheus)
Prometheus basic usage tips [link](https://www.tigera.io/learn/guides/prometheus-monitoring/prometheus-metrics/)
Grafana offical helm package [link]( https://artifacthub.io/packages/helm/grafana/grafana )
Monitoring kubernetes best practices [link](https://www.cncf.io/blog/2020/06/30/kubernetes-best-practices-for-monitoring-and-alerts/).  



### Install Prometheus

The belwo commands will install the basic Prometheus services
```helm repo add prometheus-community https://prometheus-community.github.io/helm-charts```.  
```helm repo update```.   
```helm install prometheus prometheus-community/prometheus```.  
To expose the Prometheus dashboard.   
```kubectl expose service prometheus-server — type=NodePort — target-port=9090 — name=prometheus-server-ext```.  
To port forward to your local laptop/desktop ( and aaccess via localhost:9090 ).  
```kubectl port-forward prometheus-server-6487b794-gxhn4 9090:9090```.  


### Promql
Show avaialble disk space on nodes    
```100 - ((node_filesystem_avail_bytes{mountpoint="/",fstype!="rootfs"} * 100) / node_filesystem_size_bytes{mountpoint="/",fstype!="rootfs"})```.  



### Install Grafana.   

Teh below commands will install Grafana.  
```helm repo add grafana https://grafana.github.io/helm-charts```.  
```helm repo update```.   
```helm install grafana grafana/grafana```.  
To port forward to your local laptop/desktop ( and aaccess via localhost:3000 ).  
```kubectl port-forward grafana-59fd9c8f7-9kfp6 3000:3000```.  
Obtain credetnials to access the dashabord.  
```kubectl -n default get secret grafana -o yaml ```.  
Decode the base64 user and password. (user should be admin )   
```echo -n 'S2U0cXhhajJ3NlBrcnc4WG5uN3VpT216V3E0OE90RE9ZY0FwU2NFWg==' | base64 --decode```.  
In a single command.  
```kubectl get secret --namespace default grafana -o jsonpath="{.data.admin-password}" | base64 --decode ; echo```
   


