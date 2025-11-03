# Task 1: Your First Terraform Deployment

## Objective

Create your first Infrastructure as Code project using Terraform to deploy Azure resources. Learn the fundamentals of Terraform workflow and state management.

---

## Prerequisites

- Terraform installed (or use Azure Cloud Shell)
- Azure CLI logged in
- VS Code with Terraform extension (recommended)
- Completed previous deployment tasks (for context)
- AI assistant available

---

## Your Task

### Part A: Set Up Terraform

Install and configure Terraform for Azure development.

**What you need:**
- Install Terraform CLI (if not using Cloud Shell)
- Verify installation
- Understand Terraform version


**Verify your setup:**
- Run `terraform version`
- Ensure you can run `az login`
- Check Azure CLI is authenticated

---

### Part B: Create Your First Terraform Project

Set up a basic project structure.

**Create a new directory:**
```
my-infrastructure/
```

Define Your First Resource - A Resource Group

Start simple with a resource group.

**In `main.tf`, define:**
- A resource group
- In your preferred location
- With a meaningful name

**AI assistance:**
- "How do I create an Azure resource group with Terraform?"

---

### Part C: Add Variables

Make your configuration flexible with variables. Hardcoding things sucks!

**In `variables.tf`, create variables for:**
- Resource group name
- Location
- Environment (dev/test/prod)
- Any other values you want to parameterize


**Good practices:**
- Add descriptions to all variables
- Set sensible defaults where appropriate
- Use appropriate variable types
- Add validation rules if needed

---

### Part D: Add Outputs

Export useful information from your infrastructure.

**In `outputs.tf`, output:**
- Resource group name
- Resource group ID
- Location

**Use AI to help:**
- "How do I create outputs in Terraform?"
- "What information should I output from a resource group?"
- "How do I reference resource properties in Terraform?"


---

### Part E: Initialize Terraform and Build!


**Execute:**
```
terraform init
```

**Successful output should show:**
- Provider download
- "Terraform has been successfully initialized!"

---

### Part F: Format and Validate

Ensure your code is clean and correct.

**Run formatting:**
```
terraform fmt
```
- Automatically fixes formatting
- Makes code consistent
- Should be run before every commit

**Validate syntax:**
```
terraform validate
```
- Checks for syntax errors
- Validates resource configurations
- Catches mistakes early

**AI can help:**
- "What does terraform fmt do?"
- "How do I validate Terraform code?"

---

### Part G: Plan Your Infrastructure

Preview what Terraform will create.

**Run:**
```
terraform plan
```

**What to look for:**
- Resources to be created (should be green +)
- No resources to destroy (none should exist yet)
- Review all attributes
- Check for errors

**Understanding plan output:**
- `+` = create
- `-` = destroy
- `~` = update in-place
- `-/+` = destroy and recreate

---

### Part H: Apply Your Configuration

Create your infrastructure! Use Copilot to figure this command out


**Verify in Azure:**
- Check Azure Portal
- Use Azure CLI to verify
- Compare with Terraform outputs

---


# **⚠️ Important**
- State file contains sensitive data
- Never commit to Git
- Losing state = losing track of infrastructure
- Essential for team collaboration

---

###  Make a Change

Practice the Terraform workflow with an update.

**Modify your infrastructure:**
- Add a tag to your resource group
- Or change a variable value
- Or add another resource group

**Run the workflow again:**
1. `terraform fmt`
2. `terraform validate`
3. `terraform plan` (see what will change)
4. `terraform apply` (apply the change)

---

### Exploring different Terraform Commands

Try other useful Terraform commands.

**Commands to explore:**
- `terraform show` - Display current state
- `terraform output` - Show output values
- `terraform state list` - List resources in state
- `terraform providers` - Show installed providers


This may seem boring, but learning how to use these can save you in different scenarios

---

### Part N: Destroy Resources

Learn to clean up infrastructure the correct way. 
Deleting things in the Azure portal will cause confusion in Terraform, try it if you wish!

**⚠️ Warning:** This will delete your resources!

**Run:**
```
terraform destroy
```


---

## Resources

**Official Documentation:**
- Terraform Azure Provider: registry.terraform.io/providers/hashicorp/azurerm
- Terraform Language: terraform.io/language
- Azure Resources: learn.microsoft.com/azure/templates