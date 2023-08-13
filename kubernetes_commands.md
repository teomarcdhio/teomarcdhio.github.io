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
Check if a service account has permission to do something ( get configmaps ) on all namespaces    
```kubectl auth can-i get configmaps --as=system:serviceaccount:yournamespace:serviceaccountname --all-namespaces```   
Check if a service account has permission to do something ( list pods ) on a set namespace   
```kubectl auth can-i list pods --as=system:serviceaccount:yournamespace:serviceaccountname -n yournamespace```   
Update deployment 'registry' with a new environment variable    
```kubectl set env deployment/registry STORAGE_DIR=/local```    
List the environment variables defined on a deployments 'sample-build'    
```kubectl set env deployment/sample-build --list```   
List the environment variables defined on all pods   
```kubectl set env pods --all --list```    
Run a simple pod via cli   
```kubectl run web --image=nginx```   
Create a namesapce with kubectl using inline code   
```
cat <<EOF | kubectl create -f -
apiVersion: v1
kind: Namespace
metadata:
  name: development
  labels:
    name: development
EOF
```   
List details about kubernetes node ( including instance type, region, zone, etc ).   
```kubectl get nodes -o json|jq -C '.items[] | .metadata.name,.metadata.labels'```.  
Get zones for all nodes in a eks cluster        
```kubectl get nodes -o json | jq '.items[].metadata.labels."topology.ebs.csi.aws.com/zone"' ```    
Redeploy all pods across cluster     
```kubectl rollout restart```    
Geenrate tls cert from kubeclt    
```kubectl create secret tls tls-secret --cert=path/to/tls.cert --key=path/to/tls.key```    
Kubernetes run script post container startup     
```
lifecycle:
          postStart:
            exec:
              command: ["/bin/sh", "-c", "echo '<?php phpinfo(); ?>' > index.php"]
```    

