# Task 3: Container Registries & Image Storage


## Objective

Understand where Docker images are stored, how container registries work, and practice pushing/pulling images to share them.

Remember, you will need to explain this if called on at the end! Make sure you take the time to learn about the why

---

## Prerequisites

- Docker Desktop installed and running
- GitHub Copilot or AI assistant available


---

## Where Do Images Actually Live?

### Local Storage

When you build an image, it's stored locally on your machine, but where exactly?

**Your investigation:**
- Use AI to find out where Docker stores images on your OS
- Explore the `docker image inspect` command
- Understand the difference between images and containers

**AI prompts:**
- "Where does Docker store images on macOS/Windows/Linux?"
- "What's the difference between Docker images and containers?"
- "How can I see detailed information about a Docker image?"

---

## Part A: Understanding Container Registries

Container registries are like "GitHub for Docker images" - they store and distribute container images.

### Popular Registries

**Public registries to explore:**
- Docker Hub (hub.docker.com)
- GitHub Container Registry (ghcr.io)
- Google Container Registry (gcr.io)
- Amazon ECR Public
- Red Hat Quay (quay.io)

**Research with AI:**
- "What's the difference between Docker Hub and GHCR?"
- "When should I use a private vs public registry?"
- "What are the costs of different container registries?"

---

## Your Tasks

###  Tag and Push Your Image to Azure Container Registry

**Your objective:**
- Learn about image naming conventions
- Tag your image
- Push your optimized image to ACR


**Questions to explore with AI:**
- "Why is my image push failing?"

---

### Part B: Pull and Run from ACR instead of local

Simulate deploying to a "different machine" by pulling from the registry.

**Your objective:**
- Remove your local images (optional, to test fresh pull)
- Pull the image
- Run the pulled image
- Verify it works exactly as before


---

## Registry Security

**Your objective:**
Understand security considerations for container registries.

**Topics to research with AI:**
- "What are the security risks with public Docker images?"
- "How do I scan Docker images for vulnerabilities?"
- "What is image signing and why is it important?"
- "Should I store secrets in Docker images?"