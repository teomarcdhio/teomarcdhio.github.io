---
layout: default
title: UFW Commands
parent: Linux
nav_order: 2
---
### UFW commnads

Enable the firewall   
```ufw enable```  
Disable the firewall
```ufw disable```   
Set the default incoming policy to deny all access   
```ufw default deny incoming ```    
Set the default policy to allow all outgoing connections    
```ufw default allow outgoing```    
See the current status of the firewall and see the list of rules   
```ufw status```   
Allow port 22   
```ufw allow 22```    
Block IP address 192.168.0.10   
```ufw deny from 192.168.0.10```   
Allow access to port 22 from 192.168.0.10   
```ufw allow from 192.168.0.10 to any port 22```  
Allow access to port 22 from 192.168.0.0 subnet   
```ufw allow from 192.168.0.0/24 to any port 22 ```   
Allow all incoming TCP request on port 80 and 443   
```ufw allow proto tcp from any to any port 80,443 ```  
Block outgoing packets on port 22   
```ufw deny out 22 ```   
Get the status and numbered list of rules   
```ufw status numbered ```   
Delete ruel number 3 from the list   
```ufw delete 3 ```
