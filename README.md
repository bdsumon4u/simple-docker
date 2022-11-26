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
