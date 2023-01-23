---
layout: default
title: Bash Scripts
parent: Linux
nav_order: 1
---
### Bash scripts

Sample bash script   
```
#!/bin/bash 
for i in `seq 1 90` do      
   echo $i 
done
```

Pass a file as an argument of a command; in the case below we are reading the content of the file with CAT and passing it to CAT ( afte rth epipe ) to output      
```
cat <<EOF | cat -
Sometimes I feel like thi sdoesn't work
EOF
```   
Create a namespace with kubectl using inline code   
```
cat <<EOF | kubectl create -f -
apiVersion: v1
kind: Namespace
metadata:
  name: development
  labels:
    name: development
EOF
```   

Read file line per line ( Execution: ./read_file_line_per_line.sh file_to_read.txt )   
```
#!/bin/bash
while IFS='' read -r line || [[ -n "$line" ]]; do
     echo "Text read from file: $line"
done < "$1"
```   
Check if a file exists    
```
#!/bin/bash
if [ -f $path/to/file.txt ];  then 
     echo "exist"
else 
     echo "no exist"
fi
```    
Check ip reachability
```
#!/bin/bash 
ping -w1 -c3$IP >/dev/null 2>&1 && echo "ON" || echo "OFF"
```






