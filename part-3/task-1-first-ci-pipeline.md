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

### Part A: Add Container Building

Extend your workflow to build your Docker image, we did this locally remember!


**Add steps to:**
- Replicate what you did locally to produce an image from your code

**Consider:**
- How to handle image tagging (use Git SHA?)
- How long the build takes
- What happens if the build fails

---

### Part B: Implement Testing

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

### Part C: Add More Jobs!

Learn about job dependencies and different stages

**Create multiple jobs:**
- **Test job:** Run tests and quality checks
- **Build job:** Build container image
- **Security job:** Run security scans using free oss tooling

**Configure dependencies:**
- Build job should only run if tests pass
- All jobs should run on pull requests
- Consider which jobs can run in parallel

---

### Part D: Implement Conditional Logic

Add smart conditions to your workflow. This is what things look like in the real world, sometimes we only want certain things to run on the main branch instead of inside a pull request

**Examples to implement:**
- Only build images on main branch pushes
- Skip certain jobs on unrelated file changes
- Different behavior for pull requests vs pushes

---

### Part E: Push to Azure Container Registry (Main Branch Only)

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

### Part F: Add Workflow Status Indicators (nice to have)

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
