# Task 1: Build Your First Docker Image


## Objective

Create a Docker image for your existing Node.js application and run it as a container.

Remember, you will need to explain this if called on at the end! Make sure you take the time to learn about the why

---

## Prerequisites

- Your Node.js application code (from earlier exercises)
- Docker Desktop installed and running
- GitHub Copilot or AI assistant available

---

## Your Task

### Part A: Create a Dockerfile

Using AI assistance, create a `Dockerfile` for your Node.js application.

**Requirements:**
- Use an appropriate Node.js base image
- Set up the working directory
- Install dependencies efficiently
- Copy your application code
- Expose the correct port
- Define the start command

**Suggested AI Prompts:**
- "Create a Dockerfile for my Node.js Express application"
- "What's the best base image for a Node.js 18 application?"
- "Explain each line of this Dockerfile"

---

### Part B: Build the Docker Image

Build your Docker image with a meaningful tag.

**What you need to figure out:**
- How to build a Docker image
- How to tag it appropriately
- What the build output tells you

**Use AI to help:**
- Ask about Docker build commands
- Troubleshoot any build errors
- Understand what each build step does

---

### Part C: Run Your Container

Run your containerized application and verify it works.

**Tasks:**
- Run the container with proper port mapping
- Access your application in a browser
- View the container logs
- Test your API endpoints

---

### Part D: Container Management

Explore basic Docker commands with AI assistance.

**Things to try:**
- List running containers
- Stop and start containers
- Remove containers and images
- Inspect container details

---

## Success Criteria

✅ Dockerfile created and working  
✅ Image builds without errors  
✅ Container runs successfully  
✅ Application accessible and responding  
✅ Can manage container lifecycle

---

## Discussion Points

After completing the task, be ready to discuss:

1. **What base image did you choose and why?**
2. **How does your Dockerfile handle dependencies?**
3. **What challenges did you encounter?**
4. **What did AI help you understand better?**
5. **How large is your Docker image?** (hint for next task!)

---

## Helpful Commands Reference

Use AI to explain what these do:
```bash
docker build -t [name:tag] .
docker images
docker ps
docker run -p [host]:[container] [image]
docker logs [container-id]
docker stop [container-id]
docker rm [container-id]
```

---

**Next:** Move on to Task 2 to optimize your image size!
