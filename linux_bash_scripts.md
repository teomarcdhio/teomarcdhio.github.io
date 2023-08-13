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
Return true if a bash variable is unset or set to the empty string   
```[ -z "$var" ]```    
Return true if variable is set and has value    
```[ ! -z "$var" ]```   
Bash if statement    
```#!/bin/bash
# elif statements
if [ $1 -ge 18 ]
then
echo You may go to the party.
elif [ $2 == 'yes' ]
then
echo You may go to the party but be back before midnight.
else
echo You may not go to the party.
fi
```   
Bash boolean
```
#!/bin/bash
# or example , use && for and
if [ $USER == 'bob' ] || [ $USER == 'andy' ]
then
ls -alh
else
ls
fi
```    
Bash for loop with list   
```    
LIST=(1 2 3)
for i in "${LIST[@]}"; do
    echo "example.$i"
done
```    
Bash aritmetic operation wiht variable    
```
#/bin/bash
num=20
echo "Original value: $num"
num=$((num-7))
echo "Value after subtracting 7:" $num
```    






