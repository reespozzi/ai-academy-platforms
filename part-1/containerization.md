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
  
  .gradient-border {
    border: 3px solid;
    border-image: linear-gradient(45deg, #2E8B57, #1E90FF) 1;
    padding: 1rem;
    border-radius: 8px;
  }
  
  strong {
    color: #2E8B57;
    font-weight: 600;
  }
  
  section.title {
    text-align: center;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
  
  .emoji {
    font-size: 1.5rem;
    margin-right: 0.8rem;
    display: inline-block;
    vertical-align: middle;
  }
  
  header {
    color: #666666;
    font-size: 0.9rem;
    font-weight: 500;
  }
  
  footer {
    color: #666666;
    font-size: 0.9rem;
    font-weight: 500;
  }

header: 'Containerization & Virtualization | Kainos'
footer: 'AI-Native Academy 2025'
---

# Containerization & Virtualization
## <span class="highlight">Building Modern Infrastructure</span>

---

## Why Do We Need Containers?

### **The Problem: "It works on my machine!"**

You've just built your application:
- ✅ Works perfectly on your laptop
- ❌ Crashes on your colleague's computer
- ❌ Fails when deployed to the cloud

**Why?** Different OS, dependencies, configurations, missing libraries

---

### **The Solution: Containers**

**A container packages everything your app needs:**
Your code + runtime + dependencies + system tools

**Result:** Your app runs the **exact same way** everywhere!

> Like a shipping container - travels safely anywhere, contents stay the same.

---

## Why Virtual Machines?

### **Before Containers, There Were VMs**

**The problem VMs solved:**
- One physical server = one application
- Expensive hardware sitting idle
- Difficult to isolate applications from each other

### **Virtual Machines = Multiple Computers on One Machine**

---

**A VM creates:**
- Complete isolated environments
- Each with its own operating system
- Running on shared physical hardware

**Benefits:**
- Better hardware utilization
- Strong isolation between applications
- Flexibility to run different operating systems

---

## How Virtual Machines Work
**Architecture:**
```
┌─────────────────────────────────────┐
│  VM 1       VM 2       VM 3         │
│ (Windows)  (Linux)   (MacOS)        │
├─────────────────────────────────────┤
│         Hypervisor                  │
│  (VMware, Hyper-V, KVM)             │
├─────────────────────────────────────┤
│         Host OS                     │
│  (Windows, Linux, MacOS)            │
├─────────────────────────────────────┤
│      Physical Hardware              │
│  (CPU, Memory, Storage, Network)    │
└─────────────────────────────────────┘
```
---


**The Hypervisor:**
- Sits between host OS and virtual machines
- Allocates physical resources to each VM
- Provides isolation between VMs
- Each VM thinks it has its own computer!

---

## How Containers Work

```
┌─────────────────────────────────────┐
│ C1             C2              C3   │
│(Node.js)    (Python)        (Java)  │
├─────────────────────────────────────┤
│      Container Engine               │
│         (Docker)                    │
├─────────────────────────────────────┤
│         Host OS                     │
│  (Linux, Windows, MacOS)            │
├─────────────────────────────────────┤
│      Physical Hardware              │
│  (CPU, Memory, Storage, Network)    │
└─────────────────────────────────────┘
```

---

## Containers vs Virtual Machines

**Key difference for platform engineers:**

| Containers | Virtual Machines |
|------------|------------------|
| Share host OS kernel | Each VM has full OS |
| Lightweight (MBs) | Heavy (GBs) |
| Start in seconds | Start in minutes |
| More efficient | More overhead |

**Why containers?** Portable, consistent, efficient, fast to deploy

---

## Docker Essentials

### <span class="emoji">🐳</span> **Docker = Industry Standard**

**Core concepts you need to know:**
- **Images** - Blueprint/template (read-only, built from a Dockerfile)
- **Containers** - Running instances of images (your actual application)
- **Registries** - Where images are stored and shared

---

## Images vs Containers

### **Understanding the Difference**

**Docker Image:**
- **Read-only** template or blueprint
- Contains your app code, dependencies, and configuration
- Built once from a Dockerfile
- Stored in registries (Docker Hub, GHCR)
- Can create many containers from one image
---


**Container:**
- **Running instance** of an image
- Your actual application executing
- Has its own writable layer
- Can start, stop, restart, delete
- Multiple containers can run from the same image

> **Analogy:** An image is like a class in programming, a container is like an object/instance of that class!

---

## Container Registries

**Container Registries (like GitHub for images):**
- Docker Hub, GitHub Container Registry (GHCR), AWS ECR, Azure ACR

**Why registries matter:**
- Share images across teams
- Version control for images  
- Deploy the same image everywhere (dev → staging → prod)

---

## Platform Engineering Essentials

### **What You Need to Know:**

**1. Image Optimization**
- Smaller images = faster deployments
- Use minimal base images (Alpine Linux)
- Remove unnecessary dependencies

---

**2. Versioning & Tagging**
- Tag images properly (v1.0.0, v1.0.1)
- Never use `:latest` in production!
- Link images to source code

**3. Security**
- Scan images for vulnerabilities
- Use trusted base images
- Run as non-root users
---

**4. Orchestration**
- Kubernetes for production scale
- Auto-scaling, self-healing, load balancing

---

## Your Tasks Today

**Learn by doing:**
1. **Build** a Docker image for your Node.js app
2. **Optimize** image size and security
3. **Push** to Container Registry
4. **Version** your images properly

**Remember:** Use AI (Copilot) to help you learn!