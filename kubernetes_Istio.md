---
layout: default
title: Istio
parent: Kubernetes
nav_order: 3
---
###Istio  

Install Istio Prometheus addon [link](https://istio.io/latest/docs/ops/integrations/prometheus/#option-1-quick-start)  
```kubectl apply -f https://raw.githubusercontent.com/istio/istio/release-1.16/samples/addons/prometheus.yaml```  
Validate the service is up and running   
```kubectl -n istio-system get svc prometheus```
Expose Prometheus via Istio ( replace the hostr with a valid domain resolving on the cluster )  
```
apiVersion: networking.istio.io/v1alpha3
kind: Gateway
metadata:
  name: prometheus-gateway
  namespace: istio-system
spec:
  selector:
    istio: ingressgateway
  servers:
  - port:
      number: 80
      name: http-prom
      protocol: HTTP
    hosts:
    - "!!!yourdoamin!!!"
---
apiVersion: networking.istio.io/v1alpha3
kind: VirtualService
metadata:
  name: prometheus-vs
  namespace: istio-system
spec:
  hosts:
  - "!!!yourdoamin!!!"
  gateways:
  - prometheus-gateway
  http:
  - route:
    - destination:
        host: prometheus
        port:
          number: 9090
---
apiVersion: networking.istio.io/v1alpha3
kind: DestinationRule
metadata:
  name: prometheus
  namespace: istio-system
spec:
  host: prometheus
  trafficPolicy:
    tls:
      mode: DISABLE
---
```

