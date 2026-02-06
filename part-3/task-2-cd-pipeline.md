# Task 2: Continuous Deployment Pipeline

## Objective

Now we have code that runs some tests, builds an image, maybe some more tests. How do we link it all up?


Extend your CI pipeline to automatically deploy your application image. Push to ACR and get started with deploying infrastructure with Terraform automation.

---

## Prerequisites

- Completed Task 1 (CI Pipeline)
- Working Terraform from Part 2
- Azure Container Registry


---

### Part A: Push to Azure Container Registry (Main Branch Only)

Now that you understand conditional logic, implement pushing your Docker image to Azure Container Registry, but only when code is merged to the main branch. (bonus points if you use an image tagging strategy to make images with certain tags available from a Pull Request!)

You may need to revert the change, and go back to testing if docker build works when a Pull Request is opened.

**Your task:**
- Configure Azure Container Registry credentials as GitHub secrets for now, or Azure Service Principal - what does CoPilot recommend?
- Add a job or step that pushes the built image to ACR
- Use conditional logic to ensure this only runs on main branch pushes
- Tag your image appropriately

**Key considerations:**
- Authentication to ACR (use service principal)
- Image naming conventions in ACR
- When should images be pushed vs just built?
- How to verify the push was successful?

---


### Part B: Prepare Terraform for Automation

Update your Terraform code to work in a pipeline environment, let's use a "dev" naming convention for now, since technically we're still developing things. Write your code in such a way that it will be easy to add a "prod" version of resources later!

**Make your Terraform pipeline-ready:**
- Use remote state (from Part 2 tasks)
- Add environment variables for dynamic naming - dev!
- Infrastructure folder now in your application code
- Ensure it can run without interactive input if on the main branch - plan only on branches
- Consider service principal authentication

---

### Part C: Create Terraform Deployment Job

Add a new job to deploy infrastructure automatically. We can keep a resource group only for now, we need a shell pipeline though.

What's the recommended way to authenticate to run terraform in Azure from a pipeline?

**Your Terraform job should:**
- Run after image is pushed to ACR
- Install Terraform in the runner
- Initialize and plan Terraform
- Apply infrastructure changes
- Any other recommended best practice?

Think back to conditional logic, maybe a terraform plan on branches might be useful?



Now:

✅ Image pushed conditionally to Azure Container Registry

✅ Basic Terraform workflow setup
