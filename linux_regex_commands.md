---
layout: default
title: Regex Commands
parent: Linux
nav_order: 2
---
### Regex links

Regex generator [link](https://regex101.com/)  
Log regex generator [link](https://cloud.calyptia.com/regex)

### Regex commnads

Apache logs parsing  
```127.0.0.1 - frank [10/Oct/2000:13:55:36 -0700] "GET /apache_pb.gif HTTP/1.0" 200 2326 "http://www.example.com/start.html" "Mozilla/4.08 [en] (Win98; I ;Nav)"```   
using the following regex  
```/^(?<host>[^ ]*) [^ ]* (?<user>[^ ]*) \[(?<time>[^\]]*)\] "(?<method>\S+)(?: +(?<path>[^ ]*) +\S*)?" (?<code>[^ ]*) (?<size>[^ ]*)(?: "(?<referer>[^\"]*)" "(?<agent>.*)")?$/```  
The output looks like  
```
{
  "parsed": {
    "host": "127.0.0.1",
    "user": "frank",
    "method": "GET",
    "path": "/apache_pb.gif",
    "code": "200",
    "size": "2326",
    "referer": "http://www.example.com/start.html",
    "agent": "Mozilla/4.08 [en] (Win98; I ;Nav)"
  }
}
```
