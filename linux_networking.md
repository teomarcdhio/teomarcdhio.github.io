---
layout: default
title: Networking Commands
parent: Linux
nav_order: 6
---
### Networking 

Test endpoints [link](https://pipedream.com/sources)   
Local endpoint on container [link](https://httpbin.org/)    
TcpDump cheatsheet [link](https://andreafortuna.org/2018/07/18/tcpdump-a-simple-cheatsheet/)    
Netplan docs [link](https://netplan.readthedocs.io/en/latest/examples/)     

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
Disdplay ceetificate for an endpoint   
```openssl s_client -showcerts -connect bbc.co.uk:443```   
Show what routes via specified card     
```ip route show | grep wg0```      
See open ports and associated services    
```sudo lsof -i -P -n```     
Find IP of given url     
```host -t a bbc.co.uk```   
Find MX record of given url   
```host -t mx bbc.co.uk```    
Find NS records of given url    
```host -t ns bbc.co.uk```    
Find all records of given url     
```host -a bbc.co.uk```   
Show all TCP connections and associated process   
```sudo netstat -p -at```    



### TCPDUMP    

Identify available network devices   
```tcpdump -D```   
Grab traffic from localhost and write to file ( httpbin.pcap)        
```tcpdump -i lo -w httpbin.pcap```
Grab traffic from localhost on port 80 and write to file ( httpbin.pcap)        
```tcpdump -i lo port 80 -w httpbin.pcap```  
Grab traffic from wireless card on port 80 and write to file ( httpbin.pcap)        
```tcpdump -i wlp0s20f3 port 80 -w httpbin.pcap```  
Read the tcpdump results from file    
```tcpdump -r httpbin.pcap```    
Read the tcpdump results including the body response from file    
```tcpdump -r httpbin.pcap -A```    


### NetRC

Create a file `~/.netrc` with the below content ( example for artifactory )  
```
machine artifactory.server.com
login <your-username>
password <your-password>
```
You can now use those credentials against a curl command ( or any other cli command ) by appending the -n to it.  
`curl --location --request GET 'https://artifactory.server.com/artifactory/api/v2/repositories/' -n`.  


### Ubuntu specific

Set static network ip configuration    
```sudo nano /etc/netplan/00-installer-confgi.yaml```    
populate with the block below changin your values accordingly ( routes defines your gateway )      
```
# This is the network config written by 'subiquity'
network:
  ethernets:
    ens18:
      dhcp4: no
      addresses: [192.168.0.23/24]
      nameservers:
         addresses: [8.8.8.8,192.168.0.23]
      routes:
       - to: default
         via: 192.168.0.1
  version: 2
```   
Once saved, you can run   
```sudo netplan try```    
If there are no issues, press enter to accept the new configuration.     


