# 🚀 Day 02 - Dockerizing a Node.js Application

This project demonstrates how to containerize a Node.js application using Docker. It is part of a hands-on learning series for Docker and Kubernetes.

---

## 🌐 Online Sandbox (Optional)

If you don't want to install Docker locally, you can use these platforms:

```
https://labs.play-with-docker.com/
https://labs.play-with-k8s.com/
```

---

## 💻 Install Docker

Download and install Docker Desktop from:

```
https://www.docker.com/products/docker-desktop/
```

---

## 📦 Getting Started

### 1️⃣ Clone the Repository

```
git clone https://github.com/docker/getting-started-app.git
cd getting-started-app/
```

---

### 2️⃣ Create Dockerfile

Create a new file named `Dockerfile`:

```
touch Dockerfile
```

Paste the following content:

```
FROM node:18-alpine
WORKDIR /app
COPY . .
RUN yarn install --production
CMD ["node", "src/index.js"]
EXPOSE 3000
```

---

### 3️⃣ Fix Common Error (Important ⚠️)

If you face this error:

```
Error [ERR_REQUIRE_ESM]: require() of ES Module
```

Run:

```
npm install uuid@8.3.2
```

---

### 4️⃣ Build Docker Image

```
docker build -t day02-todo .
```

Check images:

```
docker images
```

---

### 5️⃣ Push Image to Docker Hub

```
docker login
docker tag day02-todo:latest username/new-reponame:tagname
docker push username/new-reponame:tagname
```

---

### 6️⃣ Pull Image (Optional)

```
docker pull username/new-reponame:tagname
```

---

### 7️⃣ Run the Container

```
docker run -dp 3000:3000 username/new-reponame:tagname
```

---

## 🌍 Access the Application

Open your browser and visit:

```
http://localhost:3000
```

---

## 🛠️ Useful Docker Commands

### Enter Container

```
docker exec -it <container_id> sh
```

### View Logs

```
docker logs <container_id>
```


🔥 Keep going! You're building real DevOps skills step by step.
