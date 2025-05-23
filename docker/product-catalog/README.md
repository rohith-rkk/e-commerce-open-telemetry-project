**README.md**
```md
# Product Catalog Microservice

## Overview

This microservice is built using **Go** and provides a gRPC-based product catalog service. The application is containerized using **Docker** to enable easy deployment.

## Prerequisites

Before setting up the microservice, ensure you have the necessary dependencies installed:

- **Go** (Install using the command below)
  ```bash
  sudo apt install golang-go
  ```
- **Docker** (Ensure Docker is installed and running)

## Environment Variables

Set up the required environment variable before running:
```bash
export PRODUCT_CATALOG_PORT=8080
```

## Building & Running Locally (Without Docker)

1. **Build the binary:**
   ```bash
   go build -o product-catalog .
   ```
2. **Execute the microservice:**
   ```bash
   ./product-catalog
   ```

## Expected Output

Upon successful execution, logs should display:
```
info[0000] - Loaded 10 products
info[0000] - Product catalog gRPC server started on port: 8080
```

---

## Building & Running with Docker

1. **Build the Docker image:**
   ```bash
   docker build -t "your dockerusername/tag" .
   ```
2. **Verify the built image:**
   ```bash
   docker images | grep "your docker-username"
   ```
3. **Run the container:**
   ```bash
   docker run -p 8088:8088 "your dockerusername/tag"
   ```

---

## Pushing the Image to Docker Hub

1. **Log in to Docker Hub:**
   ```bash
   docker login
   ```
   Enter your credentials when prompted.

2. **Push the image to your repository:**
   ```bash
   docker push "your dockerusername/tag"
   ```

---

## Expected Output (Docker Execution)

When running inside a container, the expected logs should be:

```
info[0000] - Loaded 10 products
info[0000] - Product catalog gRPC server started on port: 8088
```

---

## License

This project is under the MIT License.
```
