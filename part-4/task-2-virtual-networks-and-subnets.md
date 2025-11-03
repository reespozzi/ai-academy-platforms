# Task 2: Virtual Networks and Subnets

## Objective

Create an Azure Virtual Network with multiple subnets. Understand network isolation and organization in Azure. Eventually deploy your container app inside segregated virtual network.

---

## Prerequisites

- Azure subscription access
- Basic Terraform knowledge from Part 2
- Understanding of IP addressing
- Working Container app deployment

---

## Your Task

### Part A: Mess around a bit!

Make a VNET in the portal with a very small IP range. Try to split this into one or more different subnets.

**Think about:**
- What IP address range for your VNet?
- How many subnets do you need?
- What size should each subnet be?
- What happens if an IP range overlaps?

---

### Part B: Replicate your setup with Terraform

Build your Virtual Network using Terraform.

**What you need:**
- Resource group
- Virtual Network resource
- Multiple subnet resources

**Use Copilot to help with:**
- Terraform syntax for VNet
- Subnet configuration
- Address space planning

---

### Part C: Add Network Security Groups

Create NSGs for each subnet with basic rules.

**Security requirements:**
- One NSG per subnet
- Allow necessary traffic
- Deny unnecessary traffic
- Document your rules

**Consider:**
- What traffic should each subnet allow?
- Should subnets talk to each other?
- What needs internet access?

---


## Success Criteria

✅ VNet created with appropriate address space  
✅ Multiple subnets configured  
✅ NSGs created and associated  
✅ Resources deployed via Terraform


---

# Update your application

You can deploy Azure Container Apps within a VNET. Can your team upgrade from the current setup, to container apps within a virtual network?

Hint: One virtual network and subnet direct mapping to one container apps environment. What architectural changes might you need?