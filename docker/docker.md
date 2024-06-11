#  Docker Commands

## Start a container
    docker run nginx
## List containers
    docker ps (running)
    docker ps -a (all)
## Stop/Remove a container
    docker stop silly_sammet 
    docker rm silly_sammet
## List images
    docker images
## Remove images
    docker rmi nginx
## Download an image
    docker pull
## Append a command
    docker run ubuntu sleep 5
## Execute a command
    docker exec distracted_mcclintock cat /etc/hosts
## Detach/Attach state
    docker run –d kodekloud/simple-webapp 
    docker attach a043d 