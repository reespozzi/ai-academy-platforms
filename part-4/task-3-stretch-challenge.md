# Task 3: Stretch Challenge

## Objective

For those who complete Tasks 1 and 2 quickly - take your skills further.

---

## Prerequisites

- Completed Tasks 1 and 2
- Comfortable with Terraform
- Understanding of Azure networking basics

---


### Challenge A: Private Database Connection

Deploy Azure PostgreSQL Flexible Server and connect it privately to your Container App.

**Goals:**
- PostgreSQL in a VNet
- Container App with VNet integration
- Private communication only
- Use managed identity for authentication

**Why this matters:**
- Production databases shouldn't be public
- Private endpoints improve security
- Real-world architecture pattern

---


### Challenge B: Azure Bastion

Set up Azure Bastion for secure VM access.

**Goals:**
- Deploy Azure Bastion in your VNet
- Remove public IPs from VMs
- Access VMs through Azure Portal
- No exposed RDP/SSH ports

**Why it's better:**
- No public exposure of management ports
- Browser-based access
- Audit trail of connections