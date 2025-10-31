# Task 3: Connect Two Isolated VNets

## Objective

Create two completely isolated Virtual Networks with VMs, then enable communication between them in the simplest way possible.

---

## Prerequisites

- Completed Task 1 & 2

---

## Your Challenges

### Part A: Create Two Isolated VNets

Build two separate networks that cannot talk to each other. Remember our idea before about completely locking things down by default.

**Create:**
- Two VNets with different address spaces
- One subnet in each VNet
- One small, minimal and cheap VM in each subnet
- NSGs blocking all traffic by default

**Verify isolation:**
- VMs should not be able to ping each other
- No connectivity between VNets

---

### Part B: Enable Connectivity

Make the VMs able to communicate using the simplest Azure feature.

**Your goal:**
- VMs can ping each other
- Maintain security (no public IPs needed)
- Use Azure's built-in networking features

**Hint:** Look into VNet peering

**Use Copilot to help you:**
- "How do I connect two VNets in Azure?"
- "What is VNet peering?"
- "Terraform configuration for VNet peering"

---


## Success Criteria

✅ Two VNets deployed with VMs  
✅ Initially isolated (no communication)  
✅ Peering configured correctly  
✅ VMs can communicate via private IPs  
✅ NSG rules allow only necessary traffic