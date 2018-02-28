## docker

Docker files

### Building Docker images

    cd <dir-with-Dockerfile>
    docker build . --tag <username>/<image-name>:<version>

### Uploading to Dockerhub

    export DOCKER_ID_USER="<username>"
    docker login
    # optionally, if you haven't already
    docker tag <image>:<version> $DOCKER_ID_USER/<image>:<version>
    docker push $DOCKER_ID_USER/<image>:<version>
