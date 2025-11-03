# Task 1: Set Up Your First CI Pipeline

## Objective

Create your first automated CI pipeline using GitHub Actions.

Skip to Part H momentarily if you require a secret for any testing purposes. We may have to comment some tests out for now if they rely on other locally deployed components (db for instance). 

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

Yes, you can bring Copilot back for this bit.

Extend your workflow to build your Docker image, we did this locally remember!

**Add steps to:**
- Replicate what you did locally to produce an image from your code

**Consider:**
- How to handle image tagging (use Git SHA?)
- How long the build takes
- What happens if the build fails

---

### Part D: Implement Testing

Add automated testing to your pipeline.

**If you have tests in your application:**
- Install dependencies
- Run unit tests
- Display test results

**If you don't have tests yet:**
- Add basic linting/code quality checks that Copilot recommends

**Testing strategy:**
- Tests should run before building, how does this relate to other tasks?
- Pipeline should fail if tests fail
- Fast feedback is crucial
- Test results should be clearly visible

---

### Part E: Add More Jobs!

Learn about job dependencies and different stages

**Create multiple jobs:**
- **Test job:** Run tests and quality checks
- **Build job:** Build container image
- **Security job:** Run security scans

**Configure dependencies:**
- Build job should only run if tests pass
- All jobs should run on pull requests
- Consider which jobs can run in parallel

---

### Part F: Implement Conditional Logic

Add smart conditions to your workflow. This is what things look like in the real world, sometimes we only want certain things to run on the main branch instead of inside a pull request

**Examples to implement:**
- Only build images on main branch pushes
- Skip certain jobs on unrelated file changes
- Different behavior for pull requests vs pushes

---

### Part G: Push to Azure Container Registry (Main Branch Only)

Now that you understand conditional logic, implement pushing your Docker image to Azure Container Registry, but only when code is merged to the main branch. (bonus points if you use an image tagging strategy to make images with certain tags available from a Pull Request!)

**Your task:**
- Configure Azure Container Registry credentials as GitHub secrets for now, or Azure Service Principal
- Add a job or step that pushes the built image to ACR
- Use conditional logic to ensure this only runs on main branch pushes
- Tag your image appropriately

**Key considerations:**
- Authentication to ACR (use service principal or credentials)
- Image naming conventions in ACR
- When should images be pushed vs just built?
- How to verify the push was successful?

---

### Part H: Add Workflow Status Indicators

Make your CI status visible, this is a nice to have

**Implement:**
- Status badges in your README

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