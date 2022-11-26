## Simple Docker

```
# List running containers
docker ps

# Build an image
docker build -t simple-docker:latest .

# Run a container
docker run simple-docker:latest

# Stop a container
docker stop <container_id> # Or first unique latters

# Run a container with ports published, interactive & tty
docker run -it -p 80:3000 simple-docker:latest
```

Added GPG key: Signed commits next...

```
# Start a container
docker start <container_id> # Start in detached mode

# Run a container with a mapping volume
docker run -it -p 80:3000 -v $PWD/files:/storage/files simple-docker:latest

# Execute a shell session inside container
docker exec -it <container_id> bash

# Mount a Docker Volume inside the container folder
docker volume create simple-files # First, have it created.
docker run -it -p 80:3000 \
    -v $PWD/files:/storage/files \
    -v simple-files:/storage/more-files \
    simple-docker:latest

# Run a command, and delete the created container after exit. OneOFF --rm
docker run -it -p 80:3000 --rm \
    -v $PWD/files:/storage/files \
    -v simple-files:/storage/more-files \
    simple-docker:latest
```
