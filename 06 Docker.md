## 🐳 **Docker Commands – Complete List with Examples (DevOps Ready)**

![Image](https://assets.bytebytego.com/diagrams/0414-how-does-docker-work.png)

![Image](https://www.docker.com/app/uploads/2021/11/docker-containerized-and-vm-transparent-bg.png)

![Image](https://miro.medium.com/0%2AzdJ9qhUzq8CmtnLH.jpeg)

![Image](https://raw.githubusercontent.com/sangam14/dockercheatsheets/master/dockercheatsheet8.png)

Below is a **practical, interview-ready + hands-on Docker command reference**, ideal for **DevOps engineers, cloud architects, and learners**.

---

## 📦 1. Docker Version & System Info

```bash
docker --version
docker version
docker info
```

**Example**

```bash
docker info | grep Server
```

---

## 🖼️ 2. Docker Images Commands

### List Images

```bash
docker images
docker image ls
```

### Pull Image

```bash
docker pull nginx
docker pull ubuntu:22.04
```

### Remove Image

```bash
docker rmi nginx
docker rmi -f IMAGE_ID
```

### Build Image

```bash
docker build -t myapp:1.0 .
```

### Inspect Image

```bash
docker inspect nginx
```

### Image History

```bash
docker history nginx
```

---

## 📦 3. Docker Containers Commands

### Run Container

```bash
docker run nginx
docker run -d nginx
docker run -d -p 8080:80 nginx
```

### Run with Name

```bash
docker run --name web -d nginx
```

### List Containers

```bash
docker ps
docker ps -a
```

### Stop / Start Container

```bash
docker stop web
docker start web
```

### Restart Container

```bash
docker restart web
```

### Remove Container

```bash
docker rm web
docker rm -f web
```

### Inspect Container

```bash
docker inspect web
```

---

## 🧑‍💻 4. Accessing Containers

### Execute Command Inside Container

```bash
docker exec -it web bash
docker exec -it web sh
```

### View Logs

```bash
docker logs web
docker logs -f web
```

---

## 🗂️ 5. Docker Volumes (Persistent Storage)

### List Volumes

```bash
docker volume ls
```

### Create Volume

```bash
docker volume create mydata
```

### Use Volume

```bash
docker run -d -v mydata:/var/lib/mysql mysql
```

### Remove Volume

```bash
docker volume rm mydata
```

---

## 🌐 6. Docker Networking

### List Networks

```bash
docker network ls
```

### Create Network

```bash
docker network create mynet
```

### Run Container in Network

```bash
docker run -d --network mynet nginx
```

### Inspect Network

```bash
docker network inspect mynet
```

---

## 📄 7. Dockerfile – Common Instructions

```dockerfile
FROM ubuntu:22.04
WORKDIR /app
COPY . .
RUN apt update && apt install -y nginx
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
```

### Build & Run

```bash
docker build -t custom-nginx .
docker run -d -p 8080:80 custom-nginx
```

---

## 🧹 8. Cleanup & Prune Commands (Very Important)

### Remove Unused Containers

```bash
docker container prune
```

### Remove Unused Images

```bash
docker image prune
docker image prune -a
```

### Remove Everything (Careful!)

```bash
docker system prune
docker system prune -a
```

---

## 📤 9. Docker Registry (Docker Hub)

### Login

```bash
docker login
```

### Tag Image

```bash
docker tag myapp:1.0 username/myapp:1.0
```

### Push Image

```bash
docker push username/myapp:1.0
```

---

## 🧪 10. Useful Debug & Monitoring Commands

```bash
docker stats
docker top web
docker events
docker diff web
```

---

## 🧠 11. Common DevOps Use Cases

### Run App in Background

```bash
docker run -d -p 3000:3000 node-app
```

### Environment Variables

```bash
docker run -e ENV=prod nginx
```

### Restart Policy

```bash
docker run --restart=always nginx
```

---

## 📌 12. Docker Command Summary (Quick Table)

| Category  | Command                                               |
| --------- | ----------------------------------------------------- |
| Image     | `docker images`, `docker pull`, `docker build`        |
| Container | `docker run`, `docker ps`, `docker stop`, `docker rm` |
| Exec      | `docker exec -it`                                     |
| Logs      | `docker logs`                                         |
| Volume    | `docker volume create`                                |
| Network   | `docker network create`                               |
| Cleanup   | `docker system prune`                                 |

---
