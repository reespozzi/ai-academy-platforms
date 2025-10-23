# Task 2: Deploy Container Apps with Terraform

## Objective

Deploy your containerized application to Azure Container Apps using Terraform.

---

## Prerequisites

- Basic Terraform understanding
- Docker image in Azure Container Registry

---

## Your Goal

Get your application running on Azure Container Apps via Terraform.

## What You Need

Ask Copilot to help you create Terraform configurations for:

1. **Container App Environment** (the platform)  
2. **Container App** (your application)

*Optional: Log Analytics Workspace for centralized logging*

## Key Configuration

- Point to your existing ACR image
- Configure public ingress on your app's port
- Set up ACR authentication (managed identity or admin credentials)

## Workflow

1. `terraform init`
2. `terraform plan` 
3. `terraform apply`
4. Test your app URL

## Success

✅ App accessible via public URL  
✅ Deployed entirely through Terraform

---

**Cleanup:** `terraform destroy` when done

### 4. Set Up Authentication

Choose one approach for ACR access:
- **Managed Identity** (recommended) - secure, no passwords

Ask Copilot to help you implement this

### 5. Deploy and Test

1. Initialize Terraform: `terraform init`
2. Plan deployment: `terraform plan`
3. Apply configuration: `terraform apply`
4. Test your application via the generated URL

### 6. Make One Update

Practice the Terraform update workflow by changing something (replica count, image tag, etc.) and redeploying.

---

## Success Criteria

✅ Container Apps instance running in Azure  
✅ Application accessible via public URL  
✅ Deployed entirely through Terraform  
✅ Can make updates via Terraform  

