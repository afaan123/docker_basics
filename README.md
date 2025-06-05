# Docker Commands Cheat Sheet

A comprehensive guide to Docker CLI commands, from basic to advanced levels, formatted for developers and DevOps professionals.

---

## Basic Docker Commands

### Install & Version Check

```bash
docker --version      # Check Docker version
docker info           # Detailed system-wide info
```

### Docker Images

```bash
docker pull <image>               # Download image from Docker Hub
docker images                     # List all downloaded images
docker rmi <image>                # Remove image
```

### Docker Containers

```bash
docker run <image>                       # Run container from image
docker run -it <image> /bin/bash         # Run with interactive terminal
docker run -d <image>                    # Run in detached mode
docker ps                                # List running containers
docker ps -a                             # List all containers (including stopped)
docker stop <container_id>               # Stop container
docker start <container_id>              # Start stopped container
docker restart <container_id>            # Restart container
docker rm <container_id>                 # Remove container
```

---

## Intermediate Docker Commands

### Logs & Inspect

```bash
docker logs <container_id>               # Show container logs
docker inspect <container_id>            # Detailed info in JSON
docker stats                             # Real-time resource usage
```

### File Operations

```bash
docker cp <container_id>:<path> <host_path>     # Copy from container to host
docker cp <host_path> <container_id>:<path>     # Copy from host to container
```

### Execute Inside Container

```bash
docker exec -it <container_id> <command>        # Run command inside container
docker exec -it <container_id> bash             # Get bash shell access
```

---

## Dockerfile & Image Management

### Build from Dockerfile

```bash
docker build -t <name>:<tag> .
```

Example:

```bash
docker build -t myapp:1.0 .
```

### Tag & Push

```bash
docker tag <image_id> <username>/<repo>:<tag>
docker push <username>/<repo>:<tag>
```

---

## Volume Management

```bash
docker volume create myvolume

docker run -v myvolume:/data <image>

docker run -v /host/path:/container/path <image>
```

---

##  Docker Networking

```bash
docker network ls                              # List all networks
docker network create <network_name>           # Create new network
docker network connect <network> <container>   # Connect container to network
docker network inspect <network>               # Inspect network configuration
```

---

##  Docker Compose

### Example `docker-compose.yml`

```yaml
version: '3'
services:
  web:
    image: nginx
    ports:
      - "80:80"
```

### Common Commands

```bash
docker-compose up                  # Start services
docker-compose up -d               # Start in detached mode
docker-compose down                # Stop and remove services
```

---

## Cleanup Commands

```bash
docker system prune                # Remove all unused data
docker image prune                 # Remove unused images
docker volume prune                # Remove unused volumes
docker container prune             # Remove stopped containers
```

---

## Extra Tips

```bash
docker history <image>            # Show image layer history
docker diff <container_id>        # Changes made to container filesystem
docker save -o <file.tar> <image> # Save image to .tar file
docker load -i <file.tar>         # Load image from .tar file
```

---

