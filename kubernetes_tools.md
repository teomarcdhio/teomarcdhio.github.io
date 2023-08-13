---
layout: default
title: Kubernetes Tools
parent: Kubernetes
nav_order: 1
---
### Yaml to Terraform

Convert Yaml files into usable Terraform resources https://github.com/jrhouston/tfk8s    
```tfk8s -f input.yaml -o output.tf```    

### Kube lint

Check a file    
```kube-linter lint /path/to/your/yaml.yaml```   
Check a folder   
```kube-linter lint /path/to/yourfolder/```    
Run a check using a cusotm config file ( https://docs.kubelinter.io/#/configuring-kubelinter )    
```kube-linter lint pod.yaml –config kubelinter-config.yaml```    

