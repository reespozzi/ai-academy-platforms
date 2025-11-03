# Task 2: Continuous Deployment Pipeline

## Objective

Now we have code that runs some tests, builds an image, maybe some more tests, and pushes them to ACR. How do we link it all up?


Extend your CI pipeline to automatically deploy your application. Push to ACR and deploy infrastructure with Terraform automation.

---

## Prerequisites

- Completed Task 1 (CI Pipeline)
- Working Terraform from Part 2
- Azure Container Registry

---

### Part A: Prepare Terraform for Automation

Update your Terraform code to work in a pipeline environment, let's use a "dev" naming convention for now, since technically we're still developing things. Write your code in such a way that it will be easy to add a "prod" version of resources later!

**Make your Terraform pipeline-ready:**
- Use remote state (from Part 2 tasks)
- Add environment variables for dynamic naming - dev!
- Ensure it can run without interactive input
- Consider service principal authentication

---

### Part B: Create Terraform Deployment Job

Add a new job to deploy infrastructure automatically. We can keep a resource group only for now, we need a shell pipeline though.

What's the recommended way to authenticate to run terraform in Azure from a pipeline?

**Your Terraform job should:**
- Run after image is pushed to ACR
- Install Terraform in the runner
- Initialize and plan Terraform
- Apply infrastructure changes