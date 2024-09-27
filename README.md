# DockerCompose Project

This project demonstrates how to use Docker and Docker Compose to set up a simple environment with **MySQL**, **NGINX**, and **Node.js**. The services are defined in the `docker-compose.yml` file, and the folder structure includes configurations for each service.

## Services Overview

### 1. **MySQL Service**
- The `mysql` folder contains the Dockerfile and an `init.sql` script to initialize the database.
- To manage the MySQL database setup, the `init.sql` script is executed when the container is started.

### 2. **NGINX Service**
- The `nginx` folder contains the Dockerfile and `nginx.conf` configuration file.
- The Dockerfile sets up an NGINX server and uses the custom configuration (`nginx.conf`) to replace the default configuration.

### 3. **Node.js Service**
- The `node` folder contains a simple Node.js application defined in `index.js`.
- The Dockerfile builds the Node.js application and installs the dependencies specified in `package.json`.


# Docker and Docker Compose Commands

## Nginx Configuration

### Remove Default Nginx Configuration
```bash
RUN rm /etc/nginx/conf.d/default.conf
```

### Copy Custom Nginx Configuration
```bash
COPY nginx.conf /etc/nginx/conf.d
```

---

## Docker Network Management

### Create a Docker Network
```bash
docker network create --driver bridge nameNetwork
```

### List Docker Networks
```bash
docker network list
```

### Remove All Docker Networks
```bash
docker network prune
```

### Run Container in Custom Network
```bash
docker run -d --network nameNetwork --name nameContainer nameImageCreate
```

---

## Docker Compose Commands

### Start Containers Using Docker Compose
```bash
docker-compose up
```

### List Containers in Docker Compose
```bash
docker-compose ps
```

### Rebuild Images with Docker Compose
```bash
docker-compose up --build
```

### Run Docker Compose in Detached Mode
```bash
docker-compose up -d
```
