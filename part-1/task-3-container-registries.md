# Task 3: Container Registries & Image Storage


## Objective

Understand where Docker images are stored, how container registries work, and practice pushing/pulling images to share them.

Remember, you will need to explain this if called on at the end! Make sure you take the time to learn about the why

---

## Prerequisites

- Your Node.js application code (from earlier exercises)
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

## Understanding Container Registries

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

### Part A: Set Up GitHub Container Registry (GHCR)

**Your objective:**
- Create a GitHub Personal Access Token with appropriate permissions
- Login to ghcr.io from the command line
- Understand authentication for GitHub Container Registry

**Use AI to help:**
- "How do I use GitHub Container Registry?"
- "What permissions does my GitHub token need for GHCR?"
- "How do I login to ghcr.io from the CLI?"
- "What's the difference between GitHub Packages and GHCR?"



**Security MUST:** Store your token securely! Never commit it to Git.

---

### Part B: Tag and Push Your Image to GHCR

**Your objective:**
- Learn about GHCR's image naming conventions
- Tag your image for GitHub Container Registry
- Push your optimized image to GHCR
- Make your package visible (public or private)

**Understanding GHCR image tags:**
```
ghcr.io/[username]/[repository]:[tag]
```

**Important:** GHCR requires all lowercase names!

**Questions to explore with AI:**
- "How do I tag a Docker image for GHCR?"
- "What's the difference between :latest and :v1 tags?"
- "How do I push an image to GitHub Container Registry?"
- "How do I make my GHCR package public?"
- "Can I connect GHCR packages to my GitHub repository?"

**Tasks:**
- Tag your image with your username
- Push the image to GHCR
- Verify it appears in your GitHub profile under "Packages"
- Configure the package visibility (public or private)

---

### Part C: Pull and Run from GHCR

Simulate deploying to a "different machine" by pulling from the registry.

**Your objective:**
- Remove your local images (optional, to test fresh pull)
- Pull the image from GitHub Container Registry
- Run the pulled image
- Verify it works exactly as before

**Concepts to explore with AI:**
- "What happens when I docker pull an image?"
- "How does Docker know where to pull from?"
- "What are image layers and why do they matter?"
- "How does GHCR handle authentication for public vs private packages?"

**Tasks:**
- Pull your image from GHCR
- Run the container from the pulled image
- Test that your application works correctly
- Understand the layer caching during pull


---

## Registry Security

**Your objective:**
Understand security considerations for container registries.

**Topics to research with AI:**
- "What are the security risks with public Docker images?"
- "How do I scan Docker images for vulnerabilities?"
- "What is image signing and why is it important?"
- "Should I store secrets in Docker images?"

**Best practices to explore:**
- ✅ Use private registries for proprietary code
- ✅ Scan images for vulnerabilities
- ✅ Use image signing (Docker Content Trust)
- ✅ Implement access controls
- ❌ Don't store secrets in images
- ❌ Don't use :latest in production

---

## 🌟 Stretch Task: Azure ACR

If you complete the main tasks and want to explore more, try pushing your image to Azure as well!

Ask for container registry name

--- 

## Discussion Points

Be ready to discuss:

1. **Why would you use multiple registries?**
2. **What's the problem with using :latest in production?**
3. **What security considerations matter for registries?**
5. **How would you implement automated cleanup of old images?**

---

**Next:** Move on to Task 4 for version control strategies!
