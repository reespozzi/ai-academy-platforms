# Task 1: Set Up Your First CI Pipeline

## Objective

Create your first automated CI pipeline using GitHub Actions.

You already have a strong CI foundation, PR workflows, automated CI check for Code Quality and tests, if so, skip to part C.

---

## Prerequisites

- GitHub repository with your application code
- Containerized application from previous parts

---

## Your Tasks

### Part A: Understand GitHub Actions Basics

Before building, understand what GitHub Actions provides.

**Key concepts to explore:**
- What are GitHub Actions and workflows?
- How do workflows trigger automatically?
- What are runners and where do they execute?
    - What different types are there and why might I want my own private one?
- How do actions work as reusable components?

**Think about going old school for this, GitHub docs online are some of the best there is!** No AI

---

### Part B: Create Your First Workflow (No AI)

Set up a basic workflow that triggers on code changes and prints something basic in the output console

**Your workflow should:**
- Trigger on pushes to main branch
- Trigger on pull requests
- Checkout your code
- Display a simple message

**Key learning:**
- YAML syntax and use
- Event triggers and when they activate
- Workflow

---

### Part C: Add Container Building

Extend your workflow to build your Docker image after everything works, we did this locally remember! Don't worry about pushing it for now. Focus on making sure the pipeline is able to build and tag your image without failing. We'll add this functionality to run on every branch for now.


**Add steps to:**
- Replicate what you did locally to produce an image from your code

**Consider:**
- How to handle image tagging (use Git SHA?)
- How long the build takes
- What happens if the build fails

---

### Part D: Add More Jobs!

Learn about job dependencies and different stages

**Create multiple jobs:**
- **Test job:** Run tests and quality checks
- **Build job:** Build container image

**Configure dependencies:**
- Build job should only run if tests pass
- Make the pipeline a little easier to read in the UI
- All jobs should run on pull requests
- Consider which jobs can run in parallel

---

### Challenge: Optimize Build Performance

Can you find a way to reduce the build time? No hints!

**Measure improvements:**
- Time before and after optimizations
- Resource usage patterns
- Bottleneck identification
- Cost implications (if using paid runners)

---

## Success Criteria

✅ Workflow triggers automatically on code changes  
✅ Container image builds successfully  
✅ Tests run and pass (or quality checks complete)  
✅ Pipeline fails appropriately when issues are detected  
✅ Status is clearly visible in repository  
✅ Can debug and fix workflow issues  
✅ Secrets are handled securely
