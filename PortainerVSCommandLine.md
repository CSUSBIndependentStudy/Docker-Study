## Overview

This lesson will compare the features of Portainer and demonstrate the simplicity it can create in your day-to-day workflow versus
using the command line for every little aspect of managing Docker. I will show the Docker command, then the equivalent feature in Portainer.

## List Containers

Use the following command to list all running containers in Docker:

```
docker ps
```
Side note: If you're wanting to list all containers (regarless of whether they're running or stopped) use:

```
docker ps -a
```
From the terminal, this is what the command prints:

![Screenshot](https://user-images.githubusercontent.com/30271499/30091366-16906546-926e-11e7-90cb-2a5f9a695e5f.JPG)

You get a list with the Container ID, Image name, Command(not important), when it was created, the status, and the ports. As you can see, I added a second container for a system monitoring utility called "Glances". 

Now, if we switch over to Portainer, this is what we can see:

![Screenshot](https://user-images.githubusercontent.com/30271499/30091521-df541e8c-926e-11e7-9024-cae68676b02c.png)
