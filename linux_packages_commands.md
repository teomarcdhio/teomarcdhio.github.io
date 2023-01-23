---
layout: default
title: Packages Commands
parent: Linux
nav_order: 1
---
### Packages commands

Install a deb application   
```sudo dpkg -i app.deb```   
List installed packages     
```sudo dpkg -l ```   
Remove package  
```sudo dpkg -r app```    
Remove package and purge config files   
```sudo dpkg -P app```     
Insert new values into the debconf database   
```echo "slapd slapd/internal/adminpw password Password123" | sudo debconf-set-selections```    
```echo "slapd slapd/organization string localdomain.com" | sudo debconf-set-selections```    
Output content set in ddebconf database
```debconf-get-selections | grep slapd```  
Install using the values stored with debconf   
```sudo DEBIAN_FRONTEND=noninteractive apt install slapd -y ```    
Query the debconf database   
```debconf-show slapd```     



