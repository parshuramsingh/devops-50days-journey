# 🚀 Day 6 – Docker Basics (DevOps 50 Days Journey)

Today, I started with **Docker** — one of the most important tools for DevOps engineers. Docker allows us to package applications with all dependencies into containers, ensuring **consistency, portability, and scalability** across environments.  

---

## 📌 Topics Covered

### # What is Docker?
- Docker is a **containerization platform**.
- A container is a **lightweight, isolated environment** that runs an application with its dependencies.
- Unlike VMs, containers share the host OS kernel → **faster & more efficient**.

---

### # Basic Docker Commands

```bash
# Check Docker version
docker --version

# Pull an image from Docker Hub
docker pull nginx

# Run a container
docker run -d -p 8080:80 nginx

# List running containers
docker ps

# List all containers (including stopped)
docker ps -a

# Stop and remove a container
docker stop <container_id>
docker rm <container_id>

# Remove an image
docker rmi nginx

# Docker Images

    An image is a blueprint for containers.

    Created using a Dockerfile.

Example Dockerfile:

# Use Node.js official image
FROM node:18-alpine

# Set working directory
WORKDIR /app

# Copy package.json and install dependencies
COPY package.json .
RUN npm install

# Copy app files
COPY . .

# Start app
CMD ["npm", "start"]

Build and run:

docker build -t my-node-app .
docker run -d -p 3000:3000 my-node-app

# Volumes (Persistent Storage)

Containers are ephemeral (data is lost when stopped).
Volumes help persist data.

# Create and mount a volume
docker run -d -p 27017:27017 -v mongo_data:/data/db mongo

Now MongoDB data persists even if the container is removed.
# Networking in Docker

    Bridge network (default): containers get internal IPs.

    Host network: shares host network stack.

    Custom networks: used for multi-container apps.

# Create a network
docker network create my-network

# Run containers inside network
docker run -d --name db --network my-network mongo
docker run -d --name app --network my-network my-node-app

Now app can reach db using container name.
# Docker Compose (Multi-Container Setup)

Instead of running multiple docker run commands, use docker-compose.yml.

version: "3"
services:
  db:
    image: mongo
    volumes:
      - mongo_data:/data/db
  app:
    build: .
    ports:
      - "3000:3000"
    depends_on:
      - db

volumes:
  mongo_data:

Run everything:

docker-compose up -d

# Useful Docker Commands

# Inspect a container
docker inspect <container_id>

# View container logs
docker logs <container_id>

# Execute commands inside a running container
docker exec -it <container_id> /bin/bash

# Clean up unused containers/images
docker system prune -a

✅ Key Takeaways

    Docker images are blueprints, containers are running instances.

    Volumes preserve persistent data.

    Networks allow multi-container communication.

    Docker Compose simplifies multi-service apps.

    Essential for CI/CD pipelines & cloud deployments.

📌 Hands-On Exercise

    Build and run a Node.js app in a container.

    Add MongoDB with persistent storage.

    Connect them using a custom network.

    Write a docker-compose.yml file to manage both together.

🔗 Resources

    Docker Documentation

Dockerfile Best Practices

Play with Docker

