# 🚀 DevOps Hands-On Learning Project (Day 1 – Day 6)

This repository documents my hands-on DevOps learning journey, focusing on Docker, CI/CD, and deployment fundamentals using free and industry-standard tools.

The goal is to build practical, job-ready DevOps skills by doing real tasks, debugging real issues, and following professional workflows.

# 🧭 What This Project Covers

  - DevOps fundamentals

  - Linux basics for DevOps

  - Docker (images, containers, Dockerfiles)

  - CI/CD using GitHub Actions

  - Secure secrets management

  - Debugging real-world Docker & CI issues

  - Deploying containerized applications locally

  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------

# 🗓️ Learning Breakdown
 # 🔹 Day 1: DevOps Foundations & Linux Basics

    - What DevOps is and why it matters

    - CI vs CD

    - DevOps lifecycle overview

    - Essential Linux commands used in DevOps

  - -Understanding automation and reliability

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

🔹 Day 2: Docker Fundamentals

What Docker is and why it’s used

Image vs Container

Dockerfile vs Image vs Container

Basic Docker commands:

docker images

docker ps

docker ps -a

docker run

docker logs

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

🔹 Day 3: Writing Dockerfiles

Structure of a Dockerfile:

FROM

WORKDIR

COPY

RUN

EXPOSE

CMD

Created Dockerfiles for:

Python applications

Node.js applications

Static HTML apps

Learned how application ports work inside containers

Importance of listening on 0.0.0.0

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

🔹 Day 4: CI/CD with GitHub Actions

What CI/CD pipelines do

GitHub Actions basics:

Workflows

Jobs

Steps

Runners

Automated:

Docker image build

Docker image push to registry

Used GitHub Secrets for secure authentication

Avoided hardcoding credentials (best practice)

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

🔹 Day 5: Debugging & Troubleshooting

Worked on real DevOps issues, including:

Port already in use errors

Docker container name conflicts

Authentication failures due to insufficient token scopes

Containers running but applications not accessible

Key debugging tools used:

docker logs
docker ps
docker ps -a
docker stop
docker rm

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

🔹 Day 6: Deploying the Application

Pulled Docker image from container registry

Ran container locally

Exposed application ports correctly

Debugged port mismatch between:

Host

Container

Application

Successfully accessed the application in a browser

Key Concept Learned
Browser → Host Port → Container Port → Application Port

🧠 Key Takeaways

Docker does not change application behavior

Port mismatches are a common production issue

Logs are the first place to debug failures

CI/CD failures are normal and fixable

Secrets must never be committed to Git

🎤 Interview Topics Demonstrated

Dockerfile creation

Image vs container lifecycle

CI/CD pipelines

GitHub Actions

Secrets management

Container networking

Debugging real-world deployment issues

🔒 Security Best Practices Followed

No credentials committed to Git

Used environment secrets for authentication

Tokens scoped with least privilege

🚀 Next Steps

Docker Compose (multi-container applications)

Kubernetes fundamentals

Cloud deployments (AWS / Azure)

Monitoring & logging

📌 Why This Repo Matters

This repository reflects real DevOps workflows, not just theory.
Every task includes hands-on execution, debugging, and fixes, similar to real production environments.