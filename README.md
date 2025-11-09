# 🐳 Docker for Beginners

![Docker](https://img.shields.io/badge/Docker-Learn-blue?logo=docker)
![License](https://img.shields.io/badge/license-MIT-green)
![Contributions](https://img.shields.io/badge/Contributions-Welcome-orange)
![Status](https://img.shields.io/badge/Status-Active-success)

> A complete hands-on guide to learn Docker — from understanding containers and images to creating your own Dockerfiles and using Docker Compose like a pro.

---

## 📚 Table of Contents

1. [Introduction](#-introduction)
2. [What is a Container?](#-what-is-a-container)
3. [Docker vs Virtual Machines](#-docker-vs-virtual-machines)
4. [Docker Image vs Container](#-docker-image-vs-container)
5. [Installing Docker](#️-installing-docker)
6. [Basic Docker Commands](#-basic-docker-commands)
7. [Creating Your First Docker Image](#-creating-your-first-docker-image)
8. [Pushing Docker Image to Docker Hub](#-pushing-docker-image-to-docker-hub)
9. [Docker Compose](#-docker-compose)
10. [Summary](#-summary)
11. [Next Steps](#-next-steps)
12. [Author](#-author)

---

## 🧠 Introduction

**Docker** is an open-source platform designed to automate the deployment of applications inside **lightweight, portable containers**.  
It enables developers to package an application and its dependencies together, ensuring consistent performance across environments.

> “Build once, run anywhere.”  

---

## 📦 What is a Container?

A **container** is an isolated environment that packages code and dependencies together.  
Unlike traditional virtual machines, containers share the host OS kernel — making them **faster**, **lighter**, and **more efficient**.

**Why use containers?**
- 🧩 Consistent across all environments  
- ⚡ Instant startup time  
- 💾 Minimal resource usage  
- 🔒 Isolated and secure  

---

## ⚔️ Docker vs Virtual Machines

| Feature | Docker (Container) | Virtual Machine |
|----------|-------------------|-----------------|
| Boot Time | Seconds | Minutes |
| Size | MBs | GBs |
| OS | Shares host kernel | Full OS per VM |
| Performance | Near-native | Slower |
| Isolation | Process-level | Hardware-level |
| Portability | High | Moderate |

✅ **Result:** Containers provide faster, smaller, and more efficient app environments.

---

## 🧩 Docker Image vs Container

| Term | Description |
|------|--------------|
| **Docker Image** | A **read-only blueprint** containing the code, runtime, libraries, and dependencies. |
| **Docker Container** | A **running instance** of an image — your app in motion. |

💡 Analogy:  
**Image → Blueprint** 🧱  
**Container → Running Building** 🏗️  

---

## ⚙️ Installing Docker

### 🪟 Windows
1. Download **Docker Desktop** → [docker.com/products/docker-desktop](https://www.docker.com/products/docker-desktop)
2. Follow the installation wizard.
3. Verify:
   ```bash
   docker --version
🐧 Linux (Ubuntu)
sudo apt update
sudo apt install docker.io -y
sudo systemctl start docker
sudo systemctl enable docker
docker --version

### 🍎 macOS

1. Download and install Docker Desktop for Mac → https://www.docker.com/products/docker-desktop
2. Verify installation:
    ```bash
   docker --version

## 🐚 Basic Docker Commands
- Command	Description
- docker --version	Show Docker version
- docker pull <image>	Download image
- docker images	List all images
- docker ps	Show running containers
- docker ps -a	Show all containers (including stopped)
- docker run <image>	Run a container
- docker stop <id>	Stop a container
- docker rm <id>	Remove a container
- docker rmi <image>	Remove an image
- docker exec -it <id> bash	Access container shell
- docker build -t <image_name> .	Build image from Dockerfile
🧱 Creating Your First Docker Image

Let’s create and run a simple Python app inside Docker 👇

1️⃣ Create app.py
print("Hello from Docker!")

2️⃣ Create Dockerfile

- Use official Python base image:
  ```bash
    FROM python:3.10-slim

- Set working directory inside the container:
  ```bash
    WORKDIR /app

- Copy all files from current directory into the container:
  ```bash
   COPY . .

- Run the app
  ```bash
   CMD ["python", "app.py"]

3️⃣ Build Docker Image:
- docker build -t hello-docker .

4️⃣ Run Docker Container:
  - docker run hello-docker


✅ Output:

Hello from Docker!

# 🚀 Pushing Docker Image to Docker Hub

1️⃣ Login to Docker Hub
- docker login

2️⃣ Tag Image
- docker tag hello-docker your_dockerhub_username/hello-docker:latest

3️⃣ Push Image
- docker push your_dockerhub_username/hello-docker:latest


✅ Verify it on Docker Hub

# 🧩 Docker Compose

Docker Compose helps you manage multiple containers with a single configuration file — docker-compose.yml.

Example: docker-compose.yml
version: '3'
services:
  web:
    image: nginx
    ports:
      - "8080:80"

  db:
    image: mysql:5.7
    environment:
      MYSQL_ROOT_PASSWORD: example

Commands:
      docker compose up     # Start all containers
      docker compose down   # Stop and remove containers

----------
🧠 Result:
This setup runs Nginx and MySQL together — one command to launch everything.

---------
# 🧭 Summary

✅ Docker → container platform for consistent deployments
✅ Containers → fast, lightweight, portable environments
✅ Images → blueprints for containers
✅ Compose → orchestrates multi-container systems

----------

# 🚀 Next Steps

Learn about Docker Volumes (persistent storage)

Explore Docker Networking

Build CI/CD pipelines using Docker

Deploy containers to AWS ECS, Kubernetes, or Azure Container Apps

# 👤 Author

👨‍💻 Aryan Khatri
B.Tech in AI & Data Science | Machine Learning & DevOps Enthusiast
📍 India

💼 LinkedIn: aryan kahtri

📧 Email: khatriaryan880@gmail.com

⭐ If you found this helpful, consider starring the repo!

🪪 License

This project is licensed under the MIT License.
Feel free to use, modify, and share it for learning purposes.

“Containers are the foundation of modern cloud-native development — start mastering them today.” 🧠🔥
