##DOCKER##

##Misc##

    Need to be sudo

##Typical work process##

    Containers are made from images. eg. from an ubuntu image.
    Images are stored in repos, just like code.
    When we create apps now we want to add our app code onto an existing image, then create and store a new image.
    Containers can then be made from that image and run on a host.

    create content of app to run in container
    pull down image from a repo to base container image on
    add code to image
    specify config, eg:
        port numbers to expose from container
        command to run

    All the above are specified in Dockerfile.
    Code and Dockerfile live in the same folder

##Search standard repo for images##

    docker search ubuntu

##Pull down container##

    docker pull ubuntu
    docker pull ubuntu:latest

        (also docker image pull ... etc)

##List installed images ##

    docker images
    docker image ls

##Create container from an image (image name and command)##

    docker run -it ubuntu /bin/bash (interactive mode)
    docker run -d ubuntu /bin/bash (detached mode)
        
    (also docker container run ... etc)

##List running containers (Shows image container made from in IMAGE col)##

    docker ps
    docker container ls
    docker container ls --no-trunc (doesn't chop off the output)

##List all containers##

    docker ps -a
    docker container ls -a

##Stop / start existing container##

    docker stop|start CONTAINER_NAME

##Create container from your own image (note there is no command specified as definded in Dockerfile where image was created from. Ports specified as host:container)##

    docker run -d --name some_great_new_image_name -p 8888:8666 image_name

##Attach to a running container (like run it)##

    docker attach CONTAINER_NAME
    docker container exec

##Exit interactive session in a container##

    ctrl pq

##Dockerfile to create an image##

    FROM node:8
    # RUN [adds stuff like installing packages etc]
    COPY nodefirst.js .
    ENTRYPOINT node nodefirst.js [command to run when the container starts]
    EXPOSE 8666

##Create image from Dockerfile##

    docker build -t imagename:latest .

##Push image to repo##

    docker push davepain/ubuntu_with_node:latest
    docker image push davepain/ubuntu_with_node:latest
    
##Create and push another tag##

    docker image tag davepain/ubuntu_with_node:v2.0
    docker image push davepain/ubuntu_with_node:v2.0
