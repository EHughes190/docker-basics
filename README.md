# Docker

Docker Desktop installed (comes with all the other bits as well). Great UI to get to grips with Docker

## COMMANDS:

==========

### BUILD

    docker build -t image-name rel-path-to-docker-file-from-curr-dir
    e.g. `docker build -t myapp .`

### RUN CONTAINERS

    NOTE: This creates a new container each time
    docker run —name container-name -p host-port:container-port image-name

    e.g. `docker run —name myapp_c1 -p 4000:4000 myapp`

    NOTE: this will run and block a terminal whilst running. See below for “detached” flag to stop this:

    `docker run —name myapp_c1 -p 4000:4000 -d myapp`

### LIST ACTIVE CONTAINERs

    `docker ps`

### LIST ALL CONTAINERS

    `docker ps -a`

### STOP CONTAINERS

    `docker stop container-id`
    OR `docker stop container-name`

### RESTART EXISITNG CONTAINERS

    `docker start container-name-or-id`
    e.g. `docker start myapp_c`
