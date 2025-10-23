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

**AI prompts:**
- "How do I install Terraform on my OS?"
- "How do I check my Terraform version?"
- "What's the latest Terraform version?"

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

**Use AI to help you create these files:**
- `providers.tf` - Azure provider configuration
- `main.tf` - Your main resources
- `variables.tf` - Input variables
- `outputs.tf` - Output values

**Suggested AI prompts:**
- "Create a Terraform providers.tf file for Azure"
- "What should I put in a Terraform providers file?"
- "Explain Terraform file structure for Azure"

**Important:** Don't copy code blindly - ask AI to explain each section!

---

### Part C: Configure the Azure Provider

Set up authentication to Azure.

**In your `providers.tf`, you need:**
- Terraform required version
- Azure provider (azurerm)
- Provider features configuration

**Authentication options:**
- Azure CLI (easiest for development for now)

**Test it:** You'll verify this works when you run `terraform init`

---

### Part D: Define Your First Resource - Resource Group

Start simple with a resource group.

**In `main.tf`, define:**
- A resource group
- In your preferred location
- With a meaningful name

**AI assistance:**
- "How do I create an Azure resource group with Terraform?"
- "Show me a Terraform resource group example"
- "What properties does an Azure resource group have?"

**Consider:**
- Naming convention (be consistent!)
- Location (use same as previous tasks)
- Tags (add tags for organization)

---

### Part E: Add Variables

Make your configuration flexible with variables.

**In `variables.tf`, create variables for:**
- Resource group name
- Location
- Environment (dev/test/prod)
- Any other values you want to parameterize

**AI prompts:**
- "How do I define variables in Terraform?"
- "What variable types does Terraform support?"
- "How do I add descriptions to Terraform variables?"

**Good practices:**
- Add descriptions to all variables
- Set sensible defaults where appropriate
- Use appropriate variable types
- Add validation rules if needed

---

### Part F: Add Outputs

Export useful information from your infrastructure.

**In `outputs.tf`, output:**
- Resource group name
- Resource group ID
- Location

**Use AI to help:**
- "How do I create outputs in Terraform?"
- "What information should I output from a resource group?"
- "How do I reference resource properties in Terraform?"

**Why outputs?**
- Display important information
- Pass values to other modules
- Use in automation scripts

---

### Part G: Initialize Terraform

Run your first Terraform command!

**Execute:**
```
terraform init
```

**What happens:**
- Downloads Azure provider
- Creates `.terraform` directory
- Prepares backend
- Sets up working directory

**If errors occur:**
- Use AI to troubleshoot
- Check your providers.tf syntax
- Verify Azure CLI is logged in

**Successful output should show:**
- Provider download
- "Terraform has been successfully initialized!"

---

### Part H: Format and Validate

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

### Part I: Plan Your Infrastructure

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

### Part J: Apply Your Configuration

Create your infrastructure!

**Run:**
```
terraform apply
```

**The process:**
- Shows plan again
- Asks for confirmation (type 'yes')
- Creates resources
- Updates state file

**What happens:**
- Azure resource group is created
- State file is generated locally
- Outputs are displayed

**Verify in Azure:**
- Check Azure Portal
- Use Azure CLI to verify
- Compare with Terraform outputs

---

### Part K: Examine the State File

Understand Terraform's state.

**Look at:**
- `terraform.tfstate` file (created after apply)
- State file structure
- Resource metadata

**⚠️ Important learnings:**
- State file contains sensitive data
- Never commit to Git without encryption
- Losing state = losing track of infrastructure
- Essential for team collaboration

---

### Part L: Make a Change

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

**Notice:**
- Terraform detects the drift
- Only changes what's necessary
- Preserves existing resources

---

### Part M: Exploring different Terraform Commands

Try other useful Terraform commands.

**Commands to explore:**
- `terraform show` - Display current state
- `terraform output` - Show output values
- `terraform state list` - List resources in state
- `terraform providers` - Show installed providers

---

### Part N: Destroy Resources

Learn to clean up infrastructure the correct way. 
Deleting things in the Azure portal will cause confusion in Terraform, try it if you wish!

**⚠️ Warning:** This will delete your resources!

**Run:**
```
terraform destroy
```

**What happens:**
- Shows what will be destroyed
- Asks for confirmation
- Deletes all managed resources
- Updates state file

**After destroy:**
- Verify resources are gone in Azure
- Check state file (should be empty)

### Part O: Destroy Resources

What to do if you only want one or two resources to be deleted from the portal?

**Hint**
- Use your typical terraform worfklow
- Code is representative of desired infrastructure state


---

## Resources

**Official Documentation:**
- Terraform Azure Provider: registry.terraform.io/providers/hashicorp/azurerm
- Terraform Language: terraform.io/language
- Azure Resources: learn.microsoft.com/azure/templates