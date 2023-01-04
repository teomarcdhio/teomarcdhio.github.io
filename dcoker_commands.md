---
layout: default
title: Docker Commands
parent: Docker
nav_order: 1
---
To create a new container; if the image is not available locally, Docker will look for a match in the DockerHub registry.  
`docker run name-of-the-container`   
To list local images.  
`docker images`   
To create a container that runs in the background use the -d flag. 
`docker run -d nginx`
To remove all local images   
```docker rmi $(docker images -a -q)```   
To give the container a unique name use --name ; this will create an Nginx container named myWebServer that runs in the background .   
```docker run -d --name myWebServer nginx```   
To create a new container and interact with it via shell.    
```docker run -it name-of-the-container bash```   
To create a new container that will delete once stopped.    
```docker run --rm -it name-of-the-container bash```  
List running containers and details such as their network port associations and unique container ID.    
```docker ps```   
Most of the following commands can be run against the name of the container or their unique ID; examples are with the unique ID.
Interact with existing container via shell.    
```docker exec -it uniqueContainerID /bin/bash```   
See container details while running.   
```docker inspect uniqueContainerID```   
Stop a container.   
```docker stop uniqueContainerID```   
Start a container.   
```docker start uniqueContainerID```
Delete a container.   
```docker rm uniqueContainerID```    
Set the container to restart in case of crash or host reboot.   
```docker run -d --name --restart=always myWebServer nginx```   
Map ports of the container to host ports with -p; this will map the host port 3100 to hit port 2368 of the container .
```docker run -d -p 3100:2368 --name myBlog ghost```
Mount volumes with -v.   
```docker run -d -p 3100:2368 --name myBlog ghost /host/directory:/container/mountpoint```   
Save docker image to a file    
```docker save -o <path for generated tar file> <image name>```
Load docker image from tar file  
```docker load -i <path to image tar file>```   
Purging All Unused or Dangling Images, Containers, Volumes, and Networks.   
```docker system prune -a```   
List all exited containers.   
```docker ps -a -f status=exited```   
Remove all exited containers.    
```docker rm $(docker ps -a -f status=exited -q)```   
List volumes.   
```docker volume ls```   
Remove volume.   
```docker volume rm volume_name```   
Display container detaisl includign laayers, env varibales, etc.   
```docker inspect continaerId```   
Show container variables   
```docker inspect -f "{{ .Config.Env }}" containerId```   
Apply changes to container image   
```docker commit --change "ENV DEBUG=true" containerId  yourcontainerimagename:tageversion```   
Login to private registry   
```docker login --username YOURUSERNAME --password-stdin YOURPASSWORD```
Copy files from container to host   
```docker cp <containerId>:/file/path/within/container /host/path/target```   
Check memory usage   
```cat /sys/fs/cgroup/memory/memory.usage_in_bytes```
Check cpu usage ( CPU time in nanoseconds )     
```cat /sys/fs/cgroup/cpu/cpuacct.usage```     
