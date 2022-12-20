---
layout: default
title: Terraform Commands
parent: Terraform
nav_order: 1
---
### Terraform commands

Destroy specific resource within a module   
```terraform destroy -target module.aws-eks.kubernetes_deployment.autoscaler```   
Create resource that depends on another resource; add the following to the resource that depends on.       
```depends_on = [aws_subnet.nameoftheresource]```   