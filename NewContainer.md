## Overview

After setting up Docker, you will need to create the containers that run the programs you want. For this we will use the "run" or "create" commands. "run" creates the container and then automatically starts it, while "create" only creates the container, but doesn't run it. For our purposes, we will use the "run" command.

## Portainer Setup

The first container we're going to setup is a for program called Portainer, which provides a detailed overview of Docker and allows you to manage containers, images, networks and volumes. With just one command, we'll be on our way towards easy Docker management. This is a must-have program for those who want to fully utilize the power of the Docker platform and API.

1. Type in this command to install and run Portainer

```
docker run -d -p 9000:9000 -v /var/run/docker.sock:/var/run/docker.sock portainer/portainer
```

I'm going to do a breakdown of what all is happening in this command. Any command that is Docker related starts with "docker" then the rest of the command. I already explained what "run" does previously. 

The "-d" flag tells Docker to run the container in background and print container ID after it's running. 

The "-p" flag publishes a container’s port(s) to the host. In this case, we'll be using port 9000, so the "9000:9000" part binds port 9000 of the container to port 9000 of the local host. 

The -v flag is for mounting the current working directory into the container. In this instance, we're mounting the location back into itself in the same location in the container. So "/var/run/docker.sock" on the local machine will also be where it points to within the Docker container's filesystem.

The final part, "portainer/portainer" is for naming purposes and telling Docker the name of the image and where to pull it from. 

2. Go to a web browser and type in 

```
<ip address where docker is located>:9000
```

For instance, if Docker is running on your local machine then type this in to access Portainer:

```
localhost:9000
```

