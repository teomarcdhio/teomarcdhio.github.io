---
layout: default
title: Helm Commands
parent: Kubernetes
nav_order: 1
---
###Helm  

Produce a sample of the chart before creatign the bundle ( from within the chart folder )
```helm template . -f values.yaml > sample.yaml```

List available helm deployments inside a namesapce  
```helm list -n namesapce```