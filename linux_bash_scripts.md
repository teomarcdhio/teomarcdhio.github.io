---
layout: default
title: Bash Scripts
parent: Linux
nav_order: 1
---
### Bash scripts

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