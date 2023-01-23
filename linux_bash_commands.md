---
layout: default
title: Bash Commands
parent: Linux
nav_order: 1
---
### Bash commands

Load and execute content of a file in the current shell ( example with .bashrc file )    
```source ~/.bashrc```   
Display files used by user   
```sudo lsof -u matteo```   
List all files by application name  
```lsof -c apache```    
List files used by a spcific process id   
```lsof -p 636```   
Tar a directory   
```tar -czvf filename.tar.gz /path/to/dir1```    
Tar all files with a set extension within the current directory   
```tar -czvf archive.tgz *.txt```   
List content of a tar file   
```tar -ztvf archive.tar.gz```   
Exctract tar file to current directory   
```tar -xzvf file.tar.gz```   
Exctract tar file to a specific directory      
```tar -xzvf file.tar.gz -C /tmp/```   
List all environment variables   
```printenv```   
Copy from remote to local host   
```scp <Username>@<IPorHost>:<PathToFile>   <LocalFileLocation>```   
Inspect file type   
```file nameOfTheFile.tar.gz```    
Find all jpeg files inside a folder   
```find /home -name *.jpg```    
Find all files edited in the last 5 days    
```find / -name "*jpg" -mtime 5```    
Find files containing the specified string; this will return content fo teh file followed by the file name    
```find . -type f -exec grep "wordyouaresearching" '{}' \; -print```   
Find files and edit their permission    
```find . -name "rc.conf" -exec chmod o+r '{}' \;```    
#### Users and groups    
Add user to a group ( dave to vboxusers group )     
```sudo usermod -a -G vboxusers dave```    
Execute a command as another user    
```sudo -uuser command```    
#### Cron jobs    
Edit cron jobs    
```crontab -e```  
#### File manipulation       
Delete first line    
```sed -i '1d' file.txt```     
Delete all empty lines    
```sed '/^$/d' file.txt```    
Delete first two characters from each line    
```cat file.txt | sed 's/^..//'```    
Delete comments and empty lines    
```sed '/ *#/d; /^$/d' file.txt```    
Delete carriage return \r    
```cat input.txt|tr -d "\r" > output.txt```    
Replace string1 with string2    
```sed -d 's/string1/string2/g' file.txt```    
Replace space by -     
```sed ':a;N;$!ba;s/\n/\'\'\-\'/g''```    
Replace line break with space    
```sed ':a;N;$!ba;s/\n/ /g'```    
Add - at the beginning of the line    
```sed -d s/^/\-/ file.txt```     
Add - at the end of the line    
```sed -d s/$/\-/ file.txt```    
Filter lines starting with a number    
```cat file.txt |grep ^[0-9]```    
Filter multiple words    
```grep -E 'string1|string2' file.txt```    
Filter multiple words old shells    
```grep -e 'string1' -e 'string2' file.txt```    
Print the third and tenth words from file    
```cat file.txt | awk '{print $3,$10}'```    
Print the third word from file separated by -     
```cat file.txt| awk -F"-" '{print $3}'```    
View only the lines that contain string1    
```sed -n '/string1/p' files.txt```    
Create symbolic link    
```ln -s/file_or_directory_path /direct_access_path```
Pretty print json files in CLI    
```cat file.json | jq```    
Print only values of the key my_key from json file    
```jq '.[] | .my_key' file.json```
 





