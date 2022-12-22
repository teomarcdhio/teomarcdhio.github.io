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


