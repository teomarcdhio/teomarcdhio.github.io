---
layout: default
title: Curl Commands
parent: Linux
nav_order: 6
---
### Curl links

Good cheat-sheet [link](https://megamorf.gitlab.io/cheat-sheets/curl/)


### Curl commands

Send HTTP header data (for example, an authorization token)   
```curl --header "Authorization: Bearer F66eD5ffXHp2Y" "https://example.com/api/v4/endpoint"```   
Make an API call to a service   
```curl --request PUT --header "PRIVATE-TOKEN: your_access_token_here" --data "?per_page=10" "https://gitlab.com/api/v4/namespaces"```   
Post data (  --data: HTTP post data, URL encoded (eg, status="Hello") )       
```curl --data "some data" http://x.com/y```   
Post data with auth   ( --user: Authentication )   
```curl -u user:pass -d status="Hello" http://twitter.com/statuses/update.xml```        
Send form data (emulates a form and Submit button)   
```curl --form "username=seth" --form "password=12345678" "https://example.com/api/v4/endpoint"```    
List content of directory        
```curl --list-only "https://example.com/foo/"```    
Fetch headers      
```curl --head "https://example.com"```   
Download a file and save it wiht original name   
```curl --remote-name "https://example.com/linux-distro.iso"```   
Download a file and save it wiht different name   
```curl --remote-name "https://example.com/linux-distro.html"  --output foo.html```    


