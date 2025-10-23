# Task 3: Remote State and Terraform Modules

## Objective

Implement remote state management and create reusable Terraform modules for team collaboration.

Get that state file out of your laptop!

---

## Prerequisites

- Completed Task 1 & 2 (Basic Terraform, Container Apps)
- Existing Terraform project

---

## Part 1: Remote State

Move your Terraform state to Azure Storage for team collaboration.

### Your Goal

Set up remote state backend in Azure Storage.

### What You Need

Ask Copilot to help you:

1. **Create Azure Storage Account** (for state storage)
2. **Configure backend block** in your Terraform
3. **Migrate existing state** to remote storage

### Key Configuration

- Storage account with blob container
- Backend configuration in `terraform` block
- State locking enabled

### Workflow

1. Create storage resources
2. Add backend configuration
3. `terraform init` (migrate state)
4. Verify state is remote

### Success

✅ State file stored in Azure Storage  
✅ State locking working  
✅ Team can share state

---

## Part 2: Terraform Modules

Turn your Container App Environment into a reusable module.

### Your Goal

Create a module for Container App Environment that others can use.

### What You Need

Ask Copilot to help you create:

1. **Module directory structure** (`modules/container-app-env/`)
2. **Module files** (main.tf, variables.tf, outputs.tf)
3. **Update main project** to use the module

### Module Design

**Inputs:** Environment name, location, resource group  
**Outputs:** Environment ID, default domain

### Workflow

1. Create module directory structure
2. Move environment resources to module
3. Update main project to call module
4. `terraform plan` and `terraform apply`

### Success

✅ Working module in modules/ directory  
✅ Main project uses the module  
✅ Can create multiple environments easily

---

**Cleanup:** `terraform destroy` when done
