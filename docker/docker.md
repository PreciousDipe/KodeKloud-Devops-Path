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
## Run – tag
    docker run redis:4.0
## RUN  - STDIN
    docker run  –i kodekloud/simple-prompt-docker (interactive mode)
    docker run  –it kodekloud/simple-prompt-docker (interactive and terminal mode)
## Run –  PORT mapping
    docker run  –p 80:5000  kodekloud/simple-webapp
    docker run  –p 3306:3306  mysql
## RUN  – Volume mapping
    docker run  –v /opt/datadir:/var/lib/mysql mysql
## Inspect Container
    docker inspect blissful_hopper
## Container Logs
    docker logs  blissful_hopper

# Running a Jenkins Container
    docker run -d -p 127.0.0.1:8080:8080 jenkins/jenkins
Use forward porting on VScode to forward the port to your browser
## Persisting data on a Container
    mkdir jenkins-data
    docker run -d -p 127.0.0.1:8080:8080 -v /root/jenkins-data:/var/jenkins_home -u root jenkins/jenkins
**create a directory in your local env and use the docker command to map**


