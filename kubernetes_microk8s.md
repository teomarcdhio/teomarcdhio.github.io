---
layout: default
title: Kubernetes MicroK8s
parent: Kubernetes
nav_order: 1
---
### Kubernetes MicroK8s

Install Microk8s   
```sudo snap install microk8s --classic --channel=1.27```   
Add user to Microk8s group   
```sudo usermod -a -G microk8s $USER```   
```sudo chown -f -R $USER ~/.kube```   
```su - $USER```   
Check status of cluster ( on the microk8s host )   
```microk8s status```   
Get kube config details to access Microk8s cluster remotely   
```microk8s config```   
Ebnable Metallb adn local storage    
```microk8s enable metallb hostpath-storage```   
Add node to cluster ( from the master node )   
```microk8s add-node```   