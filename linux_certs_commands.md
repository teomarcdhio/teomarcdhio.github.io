---
layout: default
title: Certs Commands
parent: Linux
nav_order: 1
---
### Bash commands

Generate a self signed cert usign Openssl; this will generate private key ( key.pem ) and self signed cert ( example.crt ).      
```openssl req -x509 -newkey rsa:4096 -keyout key.pem -out example.crt -sha256 -days 365 -nodes -subj "/C=UK/ST=UK/L=London/O=YourCompany/OU=Org/CN=www.yourdomain.com```      

Generate a self signed cert with Subject Alternate Name (SAN) usign Openssl; .      
```openssl req -x509 -newkey rsa:4096 -keyout key.pem -out example.crt -sha256 -days 365 -nodes -subj "/C=UK/ST=UK/L=London/O=YourCompany/OU=Org/CN=www.yourdomain.com -addext "subjectAltName=DNS:yourdomain.com,DNS:www.example.net"``` 

Obtain cert from url   
```openssl s_client -connect ${REMHOST}:${REMPORT}```    

Save website cert to file   
```echo -n | openssl s_client -connect $HOST:$PORTNUMBER -servername $SERVERNAME | openssl x509 > /tmp/$SERVERNAME.cert```   