# Task 1: Deploy Container Apps with Terraform

It's finally time to bring your apps to life and work more like a Platform Engineer

## Objective

Deploy your containerized application to Azure Container Apps using Terraform.

You will need to look into container app structures and how you may need to revisit terraform given your requirement to build two applications

**Remember:** Things should be closed to the internet by default, and opened as needed!

**Suggestion** - Spend some time reading about Container Apps, and think back to our HLD idea. Having this plan before writing your code will help

---

## Prerequisites

- Basic Terraform understanding
- Docker image in Azure Container Registry

---

## Your Goal

Get your application running on Azure Container Apps via Terraform in a CI/CD pipeline.

## What You Need

Ask Copilot to help you create Terraform configurations for:

1. **Container App Environment** (the platform)  
2. **Container Apps** (your application, remember you have an image for frontend, and an image for backend)
3. **Azure Key Vault** we can no longer define environment variable files locally, secrets must live here, and be referenced as secrets in your Container App, which can then be added as environment variables.
4. **System Assigned Managed Identity** Lives alongside your resources, used to access both key vault and ACR
5. **Access to Azure Container Registry and Key Vault** The only hint here is role assignments, you can figure the rest out!


## Key Configuration

- Point to your existing ACR images
- Configure public ingress on your frontend app
- Limit ingress on your backend app, define required port
- Set up ACR authentication and access to Key Vault (ordering will matter here! See terraform depends_on)


## Success

✅ App accessible via public URL  
✅ Backend App not accessible via public URL  
✅ Environment variables pulled as secrets from Azure Key Vault
✅ Deployed entirely through Terraform

---

# Next steps

### Deploy and Test

1. Initialize Terraform: `terraform init`
2. Plan deployment: `terraform plan`
3. Apply configuration: `terraform apply`
4. Test your application via the generated URL
5. Think about what changes you might make to your pipeline to validate a change

### Make One Update

Practice the Terraform update workflow by changing something (replica count, image tag, etc.) and redeploying.

### Time for production?

Build your container apps in more than one environment, test that it works, and then and only then go on to build your production instances.