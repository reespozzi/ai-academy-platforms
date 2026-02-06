# Task 1: Deploy Container Apps with Terraform

It's finally time to bring your apps to life and work more like a Platform Engineer. Build this out in stages, it will make your life a lot easier.

## Objective

- Deploy your containerized application to Azure Container Apps using Terraform.

- Retain the ability to feature flag

You will need to look into container app structures and how you may need to revisit terraform given your requirement to build two applications.

**Remember:** Things should be closed to the internet by default, and opened as needed!

**Suggestion** - Spend some time reading about Container Apps, and think back to our HLD idea. Having this plan before writing your code will help. You will need to build some of your resources before others, since you need to add secrets, assign roles, etc. 

**Suggestion** - Remember, you can terraform init and plan locally with no backend state to save some pipeline time if needed!

---

## Prerequisites

- Basic Terraform understanding
- Docker image in Azure Container Registry

---

## Your Goal

Get your application running on Azure Container Apps via Terraform in a CI/CD pipeline. Remember not to boil the ocean here, get something working first, and add value as you go. There is another stage after this to get a multi-environment, multi-stage full CI/CD pipeline. 

**For now, focus on getting your code into the cloud, using GitHub Actions.**

## What You Need

**Ask Copilot to help you create Terraform configurations for the following, there's an order for a reason and suggestion is to only add code for the next step once the previous is built:**

1. **Azure Key Vault** we can no longer define environment variable files locally, secrets must live here, and be referenced as secrets in your Container App, which can then be added as environment variables. Do not define this in code, build your key vault with Terraform, and manually add your secrets in the portal.
2. **User Assigned Managed Identity** Will be used to access Key Vault and Azure Container Registry.
3. **Container App Environment** (the platform)  
4. **Access to Azure Container Registry and Key Vault** The only hint here is role assignments for your managed identity, you can figure the rest out!
5. **Container Apps** (your applications, remember you have an image for frontend, and an image for backend) Only the frontend should be public facing.



## Key Configuration

- Point to your existing ACR images
- Add infrastructure directory to your repos
- Configure public ingress on your frontend app
- Limit ingress on your backend app, define required port
- Use environment variables in your container app delpoyment to toggle feature flags
- Use secrets in the [container app terraform](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/container_app#secret-1). You can then reference these in the [env](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/container_app#env-1) parameter For example;
```
....

 template {
    container {
      ....
      # Key Vault reference syntax for env vars
      env {
        name        = "SESSION_SECRET"
        secret_name = "session-secret-ref"
      }

  ...

  # Define the Key Vault references as secrets
  secret {
    name                = "session-secret-ref"
    key_vault_secret_id = "${azurerm_key_vault.frontend.vault_uri}secrets/SessionSecret"
    identity            = azurerm_user_assigned_identity.frontend.id
  }

  ....
```
Or, you can update in your code directly to pull from Azure Key Vault at runtime using the Managed Identity access. Maybe come back to this once you have things working.

- Set up ACR authentication and access to Key Vault for your managed identity using RBAC (ordering will matter here! See terraform depends_on)


## Success

✅ App accessible via public URL  

✅ Backend App not accessible via public URL  

✅ Environment variables pulled as secrets from Azure Key Vault

✅ Deployed entirely through Terraform automation

✅ Ability to toggle features on/off when deployed

---


# Next steps

### Deploy and Test

1. Run your CICD pipeline
2. Test your application via the generated URL
3. Think about what changes you might make to your pipeline to validate a change

### Make One Update

Practice the Terraform update workflow by changing something (replica count, image tag, etc.) and redeploying.


--- 

### Time for production?

Build your container apps in more than one environment, test that it works, and then and only then go on to build your production instances.

You may need to rejig your pipeline a bit to complete this.

I'm specifically not giving you more information than this, but if you get stuck we can talk about it and draw it out first!
