---
layout: default
title: Istio commands
parent: Istio
nav_order: 3
---
### Istio commands

Donwload Istio   
```curl -L https://istio.io/downloadIstio | ISTIO_VERSION=1.16.1 TARGET_ARCH=x86_64 sh -```   
Install Istio to cluster ( from within the Istio folder )    
```export PATH=$PWD/bin:$PATH```     
```istioctl install -y```   
Uninstall Istio from cluster   
```istioctl x uninstall --purge```   
Enable extra logs via telemtry    
```apiVersion: telemetry.istio.io/v1alpha1
kind: Telemetry
metadata:
  name: mesh-default
  namespace: istio-system
spec:
  accessLogging:
    - providers:
      - name: envoy```   

      