# Task 2: Continuous Deployment Pipeline

## Objective

Extend your CI pipeline to automatically deploy your application. Push to ACR and deploy infrastructure with Terraform automation.

---

## Prerequisites

- Completed Task 1 (CI Pipeline)
- Working Terraform from Part 2
- Azure Container Registry

---

## Your Tasks

### Part A: Deploy Images to ACR

Extend your CI pipeline to push built images to Azure Container Registry.

**Add to your existing workflow:**
- Login to Azure Container Registry (using what?)
- Tag your image for ACR
- Push image to ACR after successful build

**Key considerations:**
- Use proper image tagging (Git SHA is good!)
- Only push on main branch (not pull requests)
- Handle authentication securely

---

### Part B: Prepare Terraform for Automation

Update your Terraform code to work in a pipeline environment, let's use a "dev" naming convention for now, since technically we're still developing things.

**Make your Terraform pipeline-ready:**
- Use remote state (from Part 2 tasks)
- Add environment variables for dynamic naming - dev!
- Ensure it can run without interactive input
- Consider service principal authentication

---

### Part C: Create Terraform Deployment Job

Add a new job to deploy infrastructure automatically.

**Your Terraform job should:**
- Run after image is pushed to ACR
- Install Terraform in the runner
- Initialize and plan Terraform
- Apply infrastructure changes
- Use the newly pushed image

---

### Part D: Handle Terraform Authentication

Set up secure authentication for Terraform in GitHub Actions.
We ran this previously using our own accounts locally, which is fine, but how does this work when we run this in a pipeline?

**Configure:**
- Azure service principal credentials
- Terraform backend authentication
- ACR access permissions (we will help you to sort this)

**Security practices:**
- Never log sensitive values

---

### Part E: Add Environment Configuration

Make your pipeline support multiple environments (dev, staging, etc).

**Implement:**
- Environment-specific variable files
- Different resource naming per environment
- Let's us test a terraform change or code change without affecting "prod"

---

### Part F: Add Deployment Validation

Verify your deployment was successful.

**Add validation steps:**
- Check if Container App is responding
- Validate image version was deployed
- Basic health check of your application

**On failure:**
- Clear error messages
- Consider automated rollback (advanced)

---

## Success Criteria

✅ Images automatically pushed to ACR on main branch  
✅ Terraform runs automatically after image push  
✅ Infrastructure deploys with new image version  
✅ Authentication handled securely  
✅ Pipeline supports multiple environments  
✅ Deployment validation confirms success  
✅ Clear visibility of deployment status