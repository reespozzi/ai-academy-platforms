---
marp: true
theme: default
paginate: true
backgroundColor: #ffffff
color: #333333
style: |
  section {
    background: #ffffff;
    font-family: 'Inter', 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    padding: 60px;
    color: #333333;
    box-sizing: border-box;
    overflow: hidden;
  }
  
  h1 {
    color: #2E8B57;
    font-size: 2.8rem;
    font-weight: 700;
    text-align: center;
    text-shadow: 0 2px 4px rgba(46, 139, 87, 0.1);
    margin-bottom: 1rem;
    line-height: 1.2;
  }
  
  h2 {
    color: #1E90FF;
    font-size: 1.8rem;
    font-weight: 600;
    margin-bottom: 1rem;
    border-bottom: 3px solid #2E8B57;
    padding-bottom: 0.5rem;
    display: inline-block;
    line-height: 1.3;
  }
  
  h3 {
    color: #2E8B57;
    font-size: 1.4rem;
    font-weight: 600;
    margin: 1rem 0 0.8rem 0;
    line-height: 1.3;
  }
  
  p, li {
    font-size: 1.1rem;
    line-height: 1.5;
    color: #444444;
    margin: 0.6rem 0;
  }
  
  blockquote {
    background: rgba(46, 139, 87, 0.05);
    border-left: 5px solid #2E8B57;
    padding: 1rem;
    margin: 1rem 0;
    border-radius: 8px;
    font-style: italic;
    font-size: 1rem;
    color: #333333;
    line-height: 1.4;
  }
  
  table {
    background: #ffffff;
    border-radius: 12px;
    overflow: hidden;
    border: 2px solid rgba(46, 139, 87, 0.2);
    box-shadow: 0 4px 12px rgba(46, 139, 87, 0.1);
    font-size: 0.95rem;
  }
  
  th {
    background: #2E8B57;
    color: #ffffff;
    font-weight: 600;
    padding: 0.8rem;
    font-size: 1rem;
  }
  
  td {
    padding: 0.8rem;
    border-bottom: 1px solid rgba(46, 139, 87, 0.1);
    color: #444444;
  }
  
  ul, ol {
    margin: 0.8rem 0;
    padding-left: 1.5rem;
  }
  
  li {
    margin: 0.5rem 0;
    padding-left: 0.3rem;
  }
  
  code {
    background: rgba(46, 139, 87, 0.1);
    color: #2E8B57;
    padding: 0.3rem 0.6rem;
    border-radius: 4px;
    font-family: 'JetBrains Mono', 'Fira Code', monospace;
  }
  
  .highlight {
    background: linear-gradient(45deg, #2E8B57, #1E90FF, #00CED1);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    font-weight: 700;
    background-size: 200% 200%;
    animation: gradientShift 3s ease-in-out infinite;
  }
  
  @keyframes gradientShift {
    0%, 100% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
  }
  
  .blue-text {
    color: #1E90FF;
    font-weight: 600;
  }
  
  .green-text {
    color: #2E8B57;
    font-weight: 600;
  }
  
  strong {
    color: #2E8B57;
    font-weight: 600;
  }

header: 'Azure Fundamentals | Kainos'
footer: 'AI-Native Academy 2025'
---

# All (some) about Azure!
## <span class="highlight">Networking, Security & Services</span>

---

## So far

- Deployed containers to Azure
- Used Terraform for our infrastructure
- Built CI/CD pipelines

---

### **What's Missing?**

A deeper understanding the **underlying Azure foundation**.

We don't always have the option of using the nice, shiny solution. Sometimes we have to pick up existing work, or we're forced to build something in another layer of detail.

- How does networking look in the cloud?
- How do we secure these things on the internet? Should they even be on the internet?
- What other services should we consider?

---

## Networking at a Glance

---

### **Virtual Networks (VNets)**

Think of it as your own **private network in the cloud**

- Completely isolated from other customers and the internet
- You control the IP address space
- Resources communicate securely within the VNet

---

### **Subnets**

**Shortened word for "Subset of a Virtual Network"**

Divide your available IP address space into smaller chunks to get more granularity

A bit like having lockers at the gym!

---

**IP address ranges:**

```
VNet: 10.0.0.0/16
├── Web subnet: 10.0.1.0/24
├── App subnet: 10.0.2.0/24
└── Data subnet: 10.0.3.0/24
```

Each subnet gets its own address range from the VNet

This X.X.X.X/Y notation is known as a CIDR range, remember this for asking Copilot questions

---

### **Network Security Groups (NSGs)**

**To continue the Gym analogy, this is the padlock on each locker**

Control what traffic is allowed in and out

**NSGs contain rules that:**
- Allow or deny traffic
- Based on source, destination, port, protocol
- Applied to subnets or individual resources

---

**Common NSG rules:**

| Rule | Description |
|------|-------------|
| Allow HTTPS from internet | Port 443 from anywhere |
| Allow SSH from office | Port 22 from specific IP |
| Allow database from app subnet | Port 5432 from 10.0.2.0/24 |
| Deny all other inbound | Default deny rule |

---

**Security by default:**

> NSGs follow a "deny all unless explicitly allowed" approach

This means you only open the ports you actually need. Azure gives us a default deny all, but only **after** it's opened up internally.

Best practice here is that your first rule should be to block **everything**. Then add what you need iteratively.

---

### **Public vs Private IP Addresses**

**Two types of addresses in Azure**

---

**Public IP Addresses:**
- Accessible from the internet
- Used for resources that need external access
- Cost money in Azure
- Examples: Load balancers, VMs with SSH access

---

**Private IP Addresses:**
- Only accessible within your VNet, meaningless to the outside world
- Free to use
- More secure (not exposed to internet)
- Examples: Databases, internal APIs, backend services

---

**Best practice:**

> Keep as much as possible on private IPs, only expose what absolutely needs to be public

Generally, we want to avoid anything being available to the internet as much as we can. It's on a needs-must basis

---

### **DNS Zones**

**Manage domain names in Azure**

We covered DNS basics in Part 2 - now let's look at Azure's DNS service

**Azure DNS Zones provide:**
- Host your domain in Azure
- Manage DNS records (A, CNAME, etc.)
- High availability and fast resolution
- Integration with Azure resources

---

**Two types of DNS zones:**

**Public DNS Zones:**
- Resolve names from the internet
- Example: `academy.kainos.com` → Public IP -> some resource intended for public use

**Private DNS Zones:**
- Resolve names within VNets only
- Example: `database.internal.kainos.com` → Private IP -> internal only resource

---

A reminder here that we love DNS because it is so much more flexible than a single IP address!

---

## Security

---

### **Identity and Access Management (IAM)**

**Who can do what in Azure?**

Control access to your Azure resources to different people, workloads, and automation

---

**Terminology**

- **Authentication:** ?
- **Authorization:** ?
- **Role-Based Access Control (RBAC):** ?

---

**Terminology**

- **Authentication:** Proove who you are
- **Authorization:** What you're allowed access to do
- **Role-Based Access Control (RBAC):** Assign permissions via roles


---

**Common Azure roles:**

| Role | Access Level |
|------|-------------|
| Owner | Full control, can grant access |
| Contributor | Manage resources, no access control |
| Reader | View resources only |
| Custom | Specific permissions you define |

---

**Best practice:**

> Grant the **absolute minimum permissions** needed to do the job

This is called the **principle of least privilege** and is critical in production systems. We do not need to Own a resource to see that it exists, for instance.

---

### **Service Principals**

**Identities for applications and services**

When your application needs to access Azure resources

**Use cases:**
- Terraform accessing Azure
- CI/CD pipelines deploying resources
- Applications reading from Key Vault
- Automated scripts managing infrastructure

---

**Why go to all the effort?**

- Service principals don't expire when you leave
- Can be scoped to specific resources
- Better audit trail
- No MFA interruptions for automation

---

### **Managed Identities**

**Even better than service principals**

Azure-managed identities with no credentials to manage

---
**System-assigned:**
- Tied to a specific resource (VM, Container App, etc.)
- Created and deleted with the resource
- One identity per resource

**User-assigned:**
- Standalone identity
- Can be shared across multiple resources
- Independent of resource lifecycle

---

**Why managed identities are great:**

- No passwords or secrets to manage
- Azure handles credential rotation
- More secure than storing credentials
- Simpler to use

---

### **Azure Firewall**

**Centralized network security**

A managed firewall service for your Azure resources

**Key features:**
- Filter outbound traffic
- Threat intelligence
- Application and network rules
- High availability built-in

---

**When to use Azure Firewall:**

- Need centralized security for multiple VNets
- Require advanced threat protection
- Complex routing and filtering needs
- Compliance requirements

**When NSGs are enough:**
- Simple allow/deny rules
- Resource or subnet-level filtering
- Starting out with Azure

---

## Platform as a Service (PaaS)

---

### **Azure Database for PostgreSQL Flexible Server**

**Managed PostgreSQL in Azure**

---

**Your current situation:**

PostgreSQL database running somewhere else
- Managing backups  (if at all)
- Worrying about uptime (or just assuming it will always be running)
- Handling updates
- Scaling is complex

---

**With Azure PostgreSQL Flexible Server:**

**Fully managed:**
- Automatic backups
- Point-in-time restore
- Automatic patching
- Built-in monitoring

---

**High availability:**
- Zone-redundant options
- Automatic failover
- 99.99% SLA available

**Security:**
- Encryption at rest and in transit
- VNet integration
- Private endpoints
- Azure AD authentication

---

**Flexible performance:**
- Scale compute independently
- Adjust storage on the fly
- Burstable tiers for dev/test
- Reserved capacity for production

---

### **Other PaaS Examples**

**Azure App Service:**
**Azure Functions:**
**Azure SQL Database:**
**Azure Cosmos DB:**

---

## Infrastructure as a Service (IaaS)

---

### **What is IaaS?**

**What Azure handles:**
- Physical infrastructure
- Network hardware
- Storage systems
- Datacenter maintenance

---

**What you handle:**
- Operating system
- Runtime and middleware
- Application and data
- Patching and updates

Back to the idea of Virtual Machines