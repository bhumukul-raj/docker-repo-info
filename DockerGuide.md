# Docker Command Guide

This guide contains essential Docker commands and examples for common operations.

## Basic Docker Commands

### Images
```bash
# List all images
docker images

# Pull an image
docker pull ubuntu:latest

# Remove an image
docker rmi image_name:tag

# Build an image from Dockerfile
docker build -t my_image:tag .

# Build with no cache
docker build --no-cache -t my_image:tag .
```

### Containers
```bash
# List running containers
docker ps

# List all containers (including stopped)
docker ps -a

# Run a container
docker run -d --name my_container image_name:tag

# Run with port mapping
docker run -d -p 8080:80 nginx

# Run with volume mount
docker run -v /host/path:/container/path image_name

# Stop a container
docker stop container_name

# Remove a container
docker rm container_name

# Remove container when it stops
docker run --rm image_name
```

### System & Maintenance
```bash
# Clean build cache
docker builder prune -a

# Remove all stopped containers
docker container prune

# Remove unused images
docker image prune

# Remove all unused objects (containers, images, networks, volumes)
docker system prune -a

# Show docker disk usage
docker system df
```

### Logs & Debugging
```bash
# View container logs
docker logs container_name

# Follow container logs
docker logs -f container_name

# Execute command in running container
docker exec -it container_name bash

# Inspect container details
docker inspect container_name
```

### Networks
```bash
# List networks
docker network ls

# Create a network
docker network create network_name

# Connect container to network
docker network connect network_name container_name
```

### Docker Compose
```bash
# Start services
docker-compose up -d

# Stop services
docker-compose down

# View logs
docker-compose logs

# Build and start services
docker-compose up --build
```

## Examples

### Example 1: Running a Web Server
```bash
# Run nginx with port mapping and custom name
docker run -d --name my_nginx -p 8080:80 nginx
```

### Example 2: Building a Custom Image
```bash
# Build image from current directory
docker build -t myapp:1.0 .

# Run the built image
docker run -d -p 3000:3000 myapp:1.0
```

### Example 3: Data Persistence
```bash
# Run MongoDB with volume mount
docker run -d \
  --name mongodb \
  -v mongodb_data:/data/db \
  -p 27017:27017 \
  mongo
```

### Example 4: Container Network
```bash
# Create network
docker network create myapp_network

# Run containers in network
docker run -d --name backend --network myapp_network backend_image
docker run -d --name frontend --network myapp_network frontend_image
```

## Best Practices

1. Always tag your images with specific versions
2. Use multi-stage builds to reduce image size
3. Clean up unused resources regularly
4. Use .dockerignore to exclude unnecessary files
5. Never store sensitive data in images
6. Use docker-compose for multi-container applications
7. Implement health checks for production containers
