# Docker

Docker Desktop installed (comes with all the other bits as well). Great UI to get to grips with Docker

## COMMANDS:

### BUILD IMAGE

    docker build -t <image-name> <rel-path-to-docker-file-from-curr-dir>
    e.g. `docker build -t myapp .`

    Build an image with a tag:
    `docker build -t myapp:v1 .`

### LIST IMAGES

    docker images

### RUN CONTAINERS

    NOTE: This creates a new container each time
    docker run —name <container-name> -p <host-port>:<container-port> <image-name>

    e.g. `docker run —name myapp_c1 -p 4000:4000 myapp`

    NOTE: this will run and block a terminal whilst running. See below for “detached” flag to stop this:

    `docker run —name myapp_c1 -p 4000:4000 -d myapp`

    Run a container with a specific tag version of an image:
    `docker run —name myapp_c1 -p 4000:4000 -d myapp:v1`

### LIST ACTIVE CONTAINERs

    `docker ps`

### LIST ALL CONTAINERS

    `docker ps -a`

### STOP CONTAINERS

    `docker stop <container-id>`
    OR `docker stop <container-name>`

### RESTART EXISITNG CONTAINERS

    `docker start <container-name-or-id>`
    e.g. `docker start myapp_c`

## LAYER CACHING:

    - A layer is each line of the Dockerfile, that makes up an image.
    - Docker will cache each layer, so that if an image is built again, it doesn’t have to reinstall or repeat processes it did for the previous image.
    - Once it detects a discrepancy (new code for example), Docker will recompute the layer with the discrepancy, as well as the layers that follow that layer.

## REMOVING

### REMOVE IMAGES

    Make sure the image is not in use by a container
    `docker images rm <image-name-or-id>`
    e.g. docker images rm myapp

    If image is in use by a container, we can force its removal:
    `docker images rm <image-name> -f`

### DELETE CONTAINERS

    `docker container rm <container-name>`

### PRUNE ENTIRE SYSTEM

    This removes all containers, images and volumes (plus caches)
    `docker system prune -a`
