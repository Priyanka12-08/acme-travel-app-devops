# Acme Travel App – DevOps Project

## Project Overview
This repository contains the DevOps infrastructure and CI/CD setup
for the Acme Travel web application.

## Tech Stack (Planned)
- Cloud: AWS
- IaC: Terraform
- CI/CD: GitHub Actions
- Containerization: Docker
- Orchestration: Kubernetes (EKS)
- Monitoring: Prometheus & Grafana

## Environments
- Dev
- Staging
- Production

## DevOps Responsibilities
- Infrastructure provisioning using Terraform
- CI/CD pipeline setup
- Containerization and deployments
- Monitoring and logging
- Security and cost optimization

## Current Status
- Repository initialized
- Basic project structure created

# Day 4 – Docker & CI/CD Practice Sheet

## 🎯 Objective

* Gain confidence writing Dockerfiles from scratch (Python, Node.js, Static HTML)
* Write GitHub Actions CI/CD YAML from memory
* Debug common mistakes
* Prepare interview-ready explanations

---

## 🐳 Part 1: Dockerfile Templates

### 1️⃣ Python App (Flask)

```
FROM python:3.10-slim
WORKDIR /app
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt
COPY . .
EXPOSE 5000
CMD ["python", "app.py"]
```

### 2️⃣ Node.js App (Express, port 8080)

```
FROM node:18-alpine
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
EXPOSE 8080
CMD ["node", "server.js"]
```

### 3️⃣ Static HTML (nginx)

```
FROM nginx:alpine
COPY index.html /usr/share/nginx/html/index.html
EXPOSE 80
```

### 🔑 Notes

* Pattern to remember: `FROM → WORKDIR → COPY(deps) → RUN → COPY(app) → EXPOSE → CMD`
* Always copy dependencies first for **layer caching**
* Ports: Python 5000, Node 8080, HTML 80

---

## 🧪 Part 2: CI/CD YAML Template

### Basic Workflow

```
name: CI/CD Practice Pipeline

on:
  push:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Setup Docker Buildx
        uses: docker/setup-buildx-action@v3

      - name: Build Docker image
        run: |
          cd app/python  # or node-app / static-site
          docker build -t my-app:ci .

      - name: Confirm Success
        run: echo "CI/CD Practice Successful"
```

### 🔑 Notes

* `uses:` → GitHub Action
* `run:` → command executed on runner
* `@v3/@v4` → major version (stability)
* Test workflow by pushing to GitHub

---

## 🛠 Part 3: Common Mistakes to Practice & Debug

| Mistake              | Result             | Fix                              |
| -------------------- | ------------------ | -------------------------------- |
| Wrong COPY path      | Build fails        | Correct file/folder path         |
| Missing WORKDIR      | Files go to root / | Add WORKDIR /app                 |
| Wrong port in EXPOSE | App inaccessible   | Match container port to app code |
| Missing CMD          | Container exits    | Add CMD to start app             |
| CI step missing      | Pipeline fails     | Add step in workflow             |

---

## 📝 Part 4: Self-Check Questions (Interview Prep)

1. Why is WORKDIR used?
2. Why copy dependency files before app code?
3. Difference between RUN and CMD?
4. Does EXPOSE actually publish the port?
5. What triggers the pipeline?
6. Difference between `uses` and `run`?
7. Why version GitHub Actions (@v3, @v4)?
8. What happens if a step fails?

---

## 🏆 Practice Plan for Day 4

1. Write Dockerfiles for Python, Node, HTML from memory
2. Build & run containers, debug errors
3. Write CI/CD YAML from memory, push to GitHub, observe pipeline
4. Introduce intentional mistakes & fix them
5. Practice explaining each line out loud