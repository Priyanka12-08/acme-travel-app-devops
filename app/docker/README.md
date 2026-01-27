# Docker Notes

This directory will contain Dockerfiles and container-related
configuration for the Acme Travel application.



# Day 2 – Docker (Beginner) Notes

## Objective

Learn how a DevOps engineer containerizes an application using Docker and runs it locally with proper debugging and cleanup practices.

---

## Key Concepts

### Docker

* Platform to package applications and dependencies into containers
* Solves the "works on my machine" problem

### Image vs Container

* **Image**: Blueprint (read-only)
* **Container**: Running instance of an image

### Dockerfile

* A recipe that tells Docker how to build an image
* Executed top to bottom
* Each instruction creates a layer

### Port Mapping

* Connects host machine ports to container ports
* Example: `-p 5000:5000`

---

## Project Structure Used

```
app/python/
├── app.py
├── requirements.txt
└── Dockerfile
```

---

## Files Created

### app.py

* Simple Flask web app
* Listens on port 5000
* Uses `0.0.0.0` so Docker can access it

### requirements.txt

* Lists dependencies
* Contains: `flask`

### Dockerfile (Key Instructions)

* `FROM python:3.10-slim` → lightweight base image
* `WORKDIR /app` → working directory inside container
* `COPY` → copy files into container
* `RUN` → install dependencies at build time
* `EXPOSE 5000` → document app port
* `CMD` → command to start app

---

## Commands Used

### Build Image

```bash
docker build -t acme-travel-app:v1 .
```

### Run Container

```bash
docker run -d -p 5000:5000 --name acme-travel-container acme-travel-app:v1
```

### Check Status

```bash
docker ps
docker images
```

### View Logs

```bash
docker logs acme-travel-container
```

### Stop & Remove Container

```bash
docker stop acme-travel-container
docker rm acme-travel-container
```

---

## Troubleshooting Flow

1. `docker ps`
2. `docker ps -a`
3. `docker logs <container>`
4. Check port mapping
5. Rebuild image if needed

Common issues:

* Port already in use
* Container exited
* Image not found
* App listening on wrong IP

---

## DevOps Best Practices Learned

* Clean up containers after use
* Use slim base images
* Commit Docker-related changes to GitHub
* Use clear commit messages

---

## Interview-Ready Talking Points

### Conceptual

* What is Docker and why DevOps uses it
* Image vs container
* Dockerfile purpose and common instructions
* Containers vs VMs

### Hands-On

* Building images with `docker build`
* Running containers with port mapping
* Debugging using `docker logs`
* Cleaning up environments

### Sample Interview Answer

> "I containerized a Python Flask app using Docker, built and ran the container locally, exposed ports correctly, and troubleshot issues using container logs and status checks."

---

## Outcome of Day 2

* Successfully containerized an application
* Ran and accessed it via browser
* Understood Docker basics deeply enough for interviews
* Built strong DevOps habits
