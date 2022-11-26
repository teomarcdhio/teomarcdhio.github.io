---
layout: default
title: Kubernetes Commands
parent: Kubernetes
nav_order: 1
---
### Kubernetes commands

Produce a sample of the chart before creatign the bundle ( from within the chart folder )
```helm template . -f values.yaml > sample.yaml```

List available helm deployments inside a namesapce  
```helm list -n namesapce```