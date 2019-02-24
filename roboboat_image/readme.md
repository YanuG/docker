# Docker 
This is a docker image for the Roboboat ROS workspace.


## How to Build and Run DockerFile

Step 1. Generate ssh keys 
```
ssh-keygen
```

Step 2. To build the container, type the following command in terminal 
```
docker build -t ros .
```

Step 3. To run the image type into terminal. 
```
docker run -it ros
```

Step 4. To leave the container. Type in terminal
```
exit
```

## Useful Commands

Source roboboat_workspace. Remember to do that when first run script
```
source ~/roboboat_worksapce/devel/setup.bash
```

Stopping all containers 
```
docker stop $(docker ps -aq)
```

Remove all containers
```
docker rm $(docker ps -aq)
```

Remove all images 
```
docker rmi $(docker images -q)
```
