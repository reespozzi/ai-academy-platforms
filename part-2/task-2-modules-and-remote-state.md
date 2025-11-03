# Task 2: Remote State and Terraform Modules

## Objective

Implement remote state management and learn how Terraform modules work.

Get that state file out of your laptop!

---

## Prerequisites

- Completed Task 1
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

## Part 2: Create a Simple Module

Learn how modules work by creating a reusable resource group module.

### Your Goal

Create a simple module for resource groups to understand module structure.


### What You Need

Ask Copilot to help you create:

1. **Module directory structure** (`modules/resource-group/`)
2. **Module files** (main.tf, variables.tf, outputs.tf)
3. **Use the module** in your main project

### Module Design

**Inputs:**
- Resource group name
- Location

**Outputs:**
- Resource group name
- Resource group ID

### Success

✅ Working module in modules/ directory  
✅ Main project uses the module  
✅ Understand how modules structure code