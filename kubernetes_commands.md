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

Terminate finalizer on stuck ingress controllers ( can't delete ingress )   
```kubectl patch ingress <name-of-the-ingress> -n <your-namespace> -p '{"metadata":{"finalizers":[]}}' --type=merge```   
Show all resources still attached to a naamespace   
```kubectl api-resources --verbs=list --namespaced -o name | xargs -n 1 kubectl get --show-kind --ignore-not-found -n <namespace>```   
