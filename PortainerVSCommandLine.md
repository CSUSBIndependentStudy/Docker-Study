## Overview

This lesson will compare the features of Portainer and demonstrate the simplicity it can create in your day-to-day workflow versus
using the command line for every little aspect of managing Docker. I will show the Docker command, then the equivalent feature in Portainer.

## List Containers

Use the following command to list all running containers in Docker:

```
docker ps
```
Also note: If you're wanting to list all containers (regarless of whether they're running or stopped) use:

```
docker ps -a
```
From the terminal, this is what the command prints:

![Screenshot](https://user-images.githubusercontent.com/30271499/30091366-16906546-926e-11e7-90cb-2a5f9a695e5f.JPG)

You get a list with the Container ID, Image name, Command(not important), when it was created, the status, and the ports. As you can see, I added a second container for a system monitoring utility called "Glances". 

Now, if we switch over to Portainer, this is what we can see:

![Screenshot](https://user-images.githubusercontent.com/30271499/30091521-df541e8c-926e-11e7-9024-cae68676b02c.png)

Click either the list of containers in the middle of the screen, or "Containers" on the left sidebar. You will see the same list as before, but it's now in a format that is easier to understand and more manageble.

![Screenshot](https://user-images.githubusercontent.com/30271499/30091604-4f0d4b86-926f-11e7-9298-f0876fdcec92.png)

From the top, you can see all the container management commands in one convenient location. To do each of these in the terminal, you have to type a separate command. For instance, if you want to restart the Glances container, you have to type:

```
docker restart c06f0398bce2
```
So, not only do you have to do the restart command, but if it's been a while since you looked at the container ID, you have to do another "docker ps" command to grab that, THEN you do the restart command. On Portainer, all you have to do is hit "Restart" and you're done.

Here is a list of the commands (from left to right in Portainer) you have to input manually if you choose to:
```
docker start [OPTIONS] CONTAINER [CONTAINER...]
docker stop [OPTIONS] CONTAINER [CONTAINER...]
docker kill [OPTIONS] CONTAINER [CONTAINER...]
docker restart [OPTIONS] CONTAINER [CONTAINER...]
docker pause CONTAINER [CONTAINER...]
***NO EQUIVALENT COMMAND FOR RESUME***
docker rm [OPTIONS] CONTAINER [CONTAINER...]
```

For managing images, just click on "Images" on the left sidebar, and you get a similar view as for containers. You can remove images
from here as well.

![Screenshot](https://user-images.githubusercontent.com/30271499/30091982-2addf6a0-9271-11e7-8d3b-a38f646dbc5d.png)

If you wish to remove images from the Terminal, type:
```
docker rmi [OPTIONS] IMAGE [IMAGE...]
```

I thought I'd put a screenshot of the Glances program here at the end of this lesson just to show what it is and looks like.

![Screenshot](https://user-images.githubusercontent.com/30271499/30092097-ed62f964-9271-11e7-9838-21de67c65986.png)

