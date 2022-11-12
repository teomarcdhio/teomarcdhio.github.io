---
layout: default
title: Docker basics
parent: Docker
nav_order: 2
---
To build your own custom container, you need the following:
a directory and a Dokcerfile.
The Dockerfile is where the container is defined; you would normally start from an existing base image ( like ubuntu or node like in this case ) using the FROM syntax ( in our case the first line will be FROM node:10 ).
Set your working directory inside the container with WORKDIR; this is the equivalent of a CD command in linux terminal ( in our case we will work from /usr/src/app).
Then you set files you want to import in the container; these files will ideally be in your directory already and all is needed is for you to specific where the file comes from and where does it go in the container.
will set the destination path inside the container ( in our case, as we set our workdirectory to /usr/src/app we just need to set it as ./ ) and the files needed from our local folder ( in our case the package.json and late rthe app.js ).The COPY command will copy the file across ( COPY package*.json ./ ).
At this stage to build our dependencies we use the RUN command; this command allows you to run a command inside the container. For our specific case we woudl RUN npm install .
We finally copy the rest of the folder in our container with COPY . . ( moving all the content of our dockerbuild folder to the /usr/src/app folder -- our working folder int eh container ).
Finally we expose the container port 8080 ( EXPOSE 8080 ) and we run a command with CMD passing two parameters; the command name and the file to run ( in our case node and app.js that is the application file we will run in the container - the app is a simple node webserver announcing port and host IP of the container and is avaialbel on my github account https://github.com/teomarcdhio/dockerTestApp ).
The dockerfile should look like this:
```
FROM node:10 
WORKDIR /usr/src/app 
COPY package*.json ./ 
RUN npm install 
COPY . . 
EXPOSE 8080 
CMD [ "node", "app.js" ]
```
To build the container use docker build -t yourdockerhubusername/nameof the container dockerBuildFolder/ .

The above line trigger docker to buil a container based on the dockerfile inside the dockerBuildFolder and assign a tag ( -t ) with your dockerhub username followed by the name of the actual docker container.

You can now see the container in the available images ( docker images ).

READ NEXT