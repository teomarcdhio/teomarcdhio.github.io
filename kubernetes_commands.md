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

Retrieve ingress cert and save to file   
```kubectl get secret/application-tls-ingress-cert -n istio-system  -o json | jq -r '.data."tls.crt"' | base64 -d > ingress.crt```   

Port forward a container to your local host   
```kubectl port-forward pod/podname -n namesapce 8080:8080 ```