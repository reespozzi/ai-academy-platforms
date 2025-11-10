# Task 2: Optimize Docker Image Size

## Objective

Try to reduce your Docker image size using industry best practices. Learn why image size matters and apply optimization techniques. Experiment with changes and understand the affect this has.

---

## Why Image Size Matters

**Smaller images mean:**
- ✅ Faster builds and deployments
- ✅ Reduced storage costs
- ✅ Quicker container startup times
- ✅ Less attack surface (fewer dependencies)
- ✅ Faster pulls from registries

#### For large teams or long lived solutions, this really has a huge effect.
---


## Starting Point

Check your current image size from Task 1


Your goal: **Reduce this as much as possible without losing functionality**

---

## Your Tasks

### Part A: Find and use a smaller base image 

**Your objective:**
- Research other images
- Rebuild your Docker image using this
- Compare the size difference

**Beware** Images are smaller because they have less dependencies, dependencies that your app might need
---

### Part B: Implement Multi-Stage Builds

Multi-stage builds let you separate build dependencies from runtime dependencies.

**Your objective:**
- Create a Dockerfile with multiple stages
- Use one stage for installing dependencies
- Use another stage for the final runtime image
- Copy only what's needed to the final stage

**Key concepts to explore with AI:**
- What are multi-stage builds?
- How do they reduce image size?
- What's the difference between build and runtime dependencies?

---

### Part C: Production Dependencies Only

Development dependencies bloat your image unnecessarily.

**Your objective:**
- Install only production dependencies
- Research the difference between `npm install` and `npm ci`
- Understand when to use `--only=production`

**Questions for AI:**
- "What's the difference between npm install and npm ci?"
- "How do I install only production dependencies?"
- "Should devDependencies be in my Docker image?"

---

### Part D: Create a .dockerignore File

Prevent unnecessary files from being copied into your image.

**Your objective:**
- Create a `.dockerignore` file
- Identify files/folders that shouldn't be in your image
- Rebuild and measure the impact

**What to ignore:**
- node_modules (will be installed in Docker)
- .git directory
- .env files
- Documentation files
- Test files
- Build artifacts

**Ask AI:**
- "Why do I need .dockerignore if I have .gitignore?"

---

### Part E: Layer Caching Optimization

The order of Dockerfile instructions impacts build speed and caching.

**Your objective:**
- Understand Docker layer caching
- Optimize the order of COPY commands
- Rebuild and observe caching behavior

**Key principle:** Copy files that change less frequently first!

**AI prompts to try:**
- "Explain Docker layer caching"
- "What's the best order for COPY commands in a Dockerfile?"
- "Why should I copy package.json before source code?"

---

### Part F: Security - Run as Non-Root User

Running containers as root is a security risk.

**Your objective:**
- Add a non-root user to your Dockerfile
- Switch to that user before running your application
- Verify the container runs without root privileges

**Explore with AI:**
- "How do I run a Docker container as non-root?"
- "Why shouldn't I run containers as root?"
- "Create a non-root user in Dockerfile for Node.js"

---

## Measure Your Progress
You may wish to make a bloated image first to show how different changes have an effect on size.

Create a comparison table, for example:

| Version | Technique | Size | Reduction |
|---------|-----------|------|-----------|
| v1 | Original | ~1GB | Baseline |
| v2 | Alpine | ? | ?% |
| v3 | Multi-stage | ? | ?% |
| v4 | All optimizations | ? | ?% |


---

## Success Criteria

✅ Reduced image size by at least 50%  
✅ Used Alpine or minimal base image  
✅ Implemented multi-stage build  
✅ Created `.dockerignore` file  
✅ Optimized layer caching  
✅ Running as non-root user  
✅ Container still works correctly  
✅ Can explain each optimization technique

---

## Discussion Points

Be ready to discuss:

1. **What was your biggest size reduction technique?**
2. **What trade-offs did you discover?**
3. **How does multi-stage building work?**
4. **What security improvements did you make?**
5. **How much time did layer caching save on rebuilds?**

---

## Real-World Impact

**Example calculation:** 
- A company with 50 microservices
- Original: 50 × 1GB = 50GB storage
- Optimized: 50 × 150MB = 7.5GB storage
- **Savings:** 42.5GB + faster deploys across all environments!

---

**Next:** Move on to Task 3 to learn about container registries!

---