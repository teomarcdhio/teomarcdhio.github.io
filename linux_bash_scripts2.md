---
layout: default
title: Bash Scripts
parent: Linux
nav_order: 1
---
### Bash Scripts

Sample bash script   
```
#!/bin/bash 
for i in `seq 1 90` do      
   echo $i 
done
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








