#  Kubernetes Website Deployment on AWS EC2

This is my first Kubernetes project.

I created a simple website and deployed it using **AWS EC2 + Docker + Kubernetes**.

This README explains the complete process from zero step-by-step in a simple way.

---

##  Project Architecture

```
User
 |
Internet
 |
AWS EC2
 |
Docker Container
 |
Kubernetes Pod
 |
Website
```

---

## 🛠️ Technologies Used

- AWS EC2
- Ubuntu Linux
- Docker
- Kubernetes (k3s)
- Nginx
- HTML
- GitHub

---

##  Project Structure

```
kubernetes-website-deployment-on-aws

index.html
Dockerfile
 deployment.yaml
 service.yaml
 README.md
```

---

# Step 1: Create AWS EC2 Instance

Created an EC2 server:

```
OS: Ubuntu 22.04
Instance: t3.medium
Storage: 20GB
```

Connect:

```bash
ssh -i key.pem ubuntu@PUBLIC_IP
```

---

# Step 2: Update Server

```bash
sudo apt update

sudo apt upgrade -y
```

---

# Step 3: Install Docker

```bash
sudo apt install docker.io -y
```

Check:

```bash
docker --version
```

Start Docker:

```bash
sudo systemctl start docker
```

---

# Step 4: Create Website

Create folder:

```bash
mkdir website-project

cd website-project
```

Create HTML:

```bash
nano index.html
```

Add website code.

---

# Step 5: Create Dockerfile

Create:

```bash
nano Dockerfile
```

Dockerfile:

```dockerfile
FROM nginx

COPY index.html /usr/share/nginx/html

EXPOSE 80
```

---

# Step 6: Build Docker Image

```bash
docker build -t mywebsite .
```

Check image:

```bash
docker images
```

---

# Step 7: Run Website Container

```bash
docker run -d -p 80:80 mywebsite
```

Open:

```
http://EC2_PUBLIC_IP
```

Website is running 

---

# Step 8: Install Kubernetes

Install k3s:

```bash
curl -sfL https://get.k3s.io | sh -
```

Check node:

```bash
kubectl get nodes
```

---

# Step 9: Deploy Application on Kubernetes

Apply deployment:

```bash
kubectl apply -f deployment.yaml
```

Check pods:

```bash
kubectl get pods
```

---

# Step 10: Create Service

Apply service:

```bash
kubectl apply -f service.yaml
```

Check:

```bash
kubectl get svc
```

---

# Step 11: Access Website

Open:

```
http://EC2_PUBLIC_IP:30001
```

 Website deployed successfully using Kubernetes.

---

# Useful Commands

Check pods:

```bash
kubectl get pods
```

Check services:

```bash
kubectl get svc
```

Check nodes:

```bash
kubectl get nodes
```

---

# What I Learned

✅ AWS EC2 setup  
✅ Linux commands  
✅ Docker image creation  
✅ Docker containers  
✅ Kubernetes Pods  
✅ Kubernetes Deployment  
✅ Kubernetes Services  

---

# Project Result

Successfully deployed a website using:

```
AWS EC2
+
Docker
+
Kubernetes
```

---





DevOps Engineer Learning Journey 
