---
layout: default
title: Networking Commands
parent: Linux
nav_order: 6
---
### Networking commands

Display files ( services ) for all listening ports    
```sudo lsof -i -P -n | grep LISTEN```   
Display files ( services ) listening to port 22   
```sudo lsof -i:22```        
Display internet network services   
```less /etc/services```   
List open files based on port range    
```sudo lsof -i :1-1024```   
Find network activity by user   
```sudo lsof -a -i -u www-data```   
Traffic capture with tcpdump   
```tcpdump -iinterface_namedst port portport_number-w capture.pcap```    
Listen for TCP connections on port 5050    
```netcat -l 5050```    
List listening ports on host.  
```netstat -Vnl```.  
List active network connections.  
```netstat -a```.   




### NetRC

Create a file `~/.netrc` with the below content ( example for artifactory )  
```
machine artifactory.server.com
login <your-username>
password <your-password>
```
You can now use those credentials against a curl command ( or any other cli command ) by appending the -n to it.  
`curl --location --request GET 'https://artifactory.server.com/artifactory/api/v2/repositories/' -n`.  


