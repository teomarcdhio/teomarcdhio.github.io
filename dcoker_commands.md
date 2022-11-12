---
layout: default
title: Docker Commands
parent: Docker
nav_order: 1
---
`docker run name-of-the-container`  
To create a new container; if the image is not available locally, Docker will look for a match in the DockerHub registry.  
`docker images`   
To list local images.  
`docker run -d nginx`
To create a container that runs in the background use the -d flag.
To give the container a unique name use --name docker run -d --name myWebServer nginx ; this will create an Nginx container named myWebServer that runs in the background .
To create a new container and interact with it via shell use docker run -it name-of-the-container bash .
List running containers and details such as their network port associations and unique container ID with docker ps .
Most of the following commands can be run against the name of the container or their unique ID; examples are with the unique ID.
Interact with existing container via shell docker exec -it uniqueContainerID /bin/bash .
See container details while running docker inspect uniqueContainerID .
Stop a container docker stop uniqueContainerID .
Start a container docker start uniqueContainerID .
Delete a container docker rm uniqueContainerID .
Set the container to restart in case of crash or host reboot docker run -d --name --restart=always myWebServer nginx .
Map ports of the container to host ports with -p docker run -d -p 3100:2368 --name myBlog ghost ; this will map the host port 3100 to hit port 2368 of the container .
Mount volumes with -v docker run -d -p 3100:2368 --name myBlog ghost /host/directory:/container/mountpoint