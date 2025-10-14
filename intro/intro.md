---
marp: true
theme: default
paginate: true
backgroundColor: #ffffff
color: #333333
style: |
  section {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    padding: 60px;
  }
  
  h1 {
    color: #2E8B57;
    font-size: 2.8rem;
    font-weight: 700;
    text-align: center;
    margin-bottom: 1.5rem;
  }
  
  h2 {
    color: #1E90FF;
    font-size: 1.8rem;
    font-weight: 600;
    border-bottom: 3px solid #2E8B57;
    padding-bottom: 0.5rem;
    margin-bottom: 1rem;
  }
  
  h3 {
    color: #2E8B57;
    font-size: 1.4rem;
    font-weight: 600;
    margin: 1rem 0;
  }
  
  ul {
    list-style: none;
    padding-left: 0;
  }
  
  li {
    padding-left: 1.5rem;
    margin: 0.8rem 0;
    position: relative;
  }
  
  li::before {
    content: "●";
    color: #2E8B57;
    font-size: 1.2rem;
    position: absolute;
    left: 0;
  }
  
  strong {
    color: #2E8B57;
    font-weight: 600;
  }
  
  blockquote {
    border-left: 5px solid #2E8B57;
    padding-left: 1rem;
    margin: 1rem 0;
    font-style: italic;
    color: #555;
  }
  
  code {
    background: #f4f4f4;
    color: #2E8B57;
    padding: 0.2rem 0.5rem;
    border-radius: 3px;
    font-family: monospace;
  }

header: 'Kainos'
footer: 'AI-Native Academy 2025 | Platform Engineering'
---

# Platform Engineering
## <span class="highlight">Building the Foundation for Developer Excellence</span>

---

## What does Platform Engineering mean to you?

---


> "Platform Engineering is the process of designing and building re-usable tools, processes and infrastructure that enables self-service capabilities for software engineering teams"

**Key Goals**: Stability, Developer Enablement & DevEx, Speed, Standardisation


---
## The Problem We're Solving

- **Developer Toil**: Too much time spent on infrastructure, tooling, and deployment
- **Inconsistent Practices**: Teams solving the same problems differently
- **Slow Delivery**: Complex deployment pipelines and environment setup
- **Security & Compliance**: Manual processes lead to gaps and risks
- **Centralised Opinionated Worldview**: What does good look like?
- **Building things!**

---


**Stability**: The business cares about uptime! 

> Builds on the agile manifesto idea that working software comes before all else.


---

**Developer Enablement**: How do we reduce the number of "I need a..." requests

> Focusses on tooling and workflows to enable developers to build the things that they need.


---


**DevEx (Developer Experience)**: Make developers' lives easier!

> Focus on reducing friction and cognitive load, how do we make using our platform the best it can be?


---


**Speed**: Metrics metrics and more metrics

> Time to first deployment, lead time for changes, deployment frequency, pipeline duration, high velocity. 


---


**Standardisation**: Consistency across teams and projects!

> Establish golden paths and best practices that reduce variability and increase predictability.


---

## Core Principles

- **Developer Self-Service** - Empower teams with autonomy
- **Golden Paths** - Opinionated, best-practice workflows
- **Abstractions** - Hide complexity, expose simplicity
- **Product Mindset** - Internal platforms as products
- **Measurement** - Data-driven platform evolution

---

## Platform Components

### 🏗️ **Infrastructure as Code**
- Terraform, Pulumi, CDK
- Standardized environments

### 🚀 **CI/CD Pipelines**
- Automated testing & deployment
- Security scanning integration

---
## Platform Components

### 📊 **Observability**
- Monitoring, logging, tracing
- Performance insights

### 🔐 **Security & Compliance**
- Policy as code
- Secret management
- Vulnerability scanning

---
## Platform Components

### 📚 **Developer Portals**
- Service catalogs
- Documentation
- Self-service workflows

### 🛠️ **Toolchain Integration**
- CLI tools
- APIs

---

## Benefits of Platform Engineering

### <span class="emoji">👩‍💻</span> For Developers
- **Faster Time to Production** - Minutes, not weeks
- **Reduced Cognitive Load** - Focus on business logic  
- **Consistent Experience** - Same tools, same patterns


---
## Benefits of Platform Engineering

### <span class="emoji">🏢</span> For Organizations
- **Improved Velocity** - Faster feature delivery
- **Better Security** - Built-in best practices
- **Cost Optimization** - Efficient resource usage

---

## The Future: AI-Native Platforms

<style scoped>
section p, section li { font-size: 0.90rem; line-height: 1.4; }
section h3 { font-size: 1.1rem; }
</style>

🤖 **Intelligent Automation**
- AI-powered incident response
- Predictive scaling
- Automated code reviews

🔮 **Next-Gen Developer Experience**
- Natural language infrastructure
- AI pair programming for ops
- Intelligent troubleshooting

---

# What **Platform Engineering** is *not*

---
## ChatGPT, how do I get my app on localhost:3000 available on the internet?

---

## Heroku

This will give you an **application available on the internet!**

What's **wrong** with this?
![w:700 h:500](heroku.png)


---

## Fast or built to last?
You  can get something "live" fast and easily. 

Platform Engineering builds the foundation for sustainable, scalable, and reliable software delivery, how we build things in the real world.
> You must think first, before you move


---


## Understanding HLD, LLD & F/NFRs

> <span class="green-text">Measure Twice, Cut Once</span>

These artifacts help us:
- Communicate design decisions
- Ensure requirements are met
- Guide implementation
- Document for future teams

---

## High-Level Design (HLD)
<style scoped>
section p, section li { font-size: 0.90rem; line-height: 1.4; }
section h3 { font-size: 1.1rem; }
</style>

**What is it?**
- Bird's-eye view of the system architecture
- Focus on major components and their interactions

**Key Contents:**
- System architecture diagrams
- Component relationships
- Data flow
- Technology stack decisions
- Integration points

---

## Low-Level Design (LLD)
<style scoped>
section p, section li { font-size: 0.75rem; line-height: 1.4; }
section h3 { font-size: 1rem; }
</style>

**What is it?**
- Detailed technical specifications
- Implementation details for each component
- APIs, data models, algorithms

**Key Contents:**
- Detailed class/module designs
- Database schemas
- API specifications (endpoints, payloads)
- Sequence diagrams
- Error handling strategies

---

## Functional Requirements (FRs)

**What are they?**
- Define WHAT the system must do
- Specific features and capabilities
- User-facing functionality and behaviors

---

**Key Aspects:**
- <span class="emoji">✅</span> **User Actions** - Login, deploy, configure
- <span class="emoji">🔄</span> **System Behaviors** - Process requests, store data
- <span class="emoji">📝</span> **Business Rules** - Validation, workflows
- <span class="emoji">🔌</span> **Integrations** - External systems, APIs

---

## Functional Requirements (FRs)

**Example FRs for a Platform:**
- Users must be able to deploy applications via CLI or UI
- System must support multiple environments (dev, staging, prod)
- Platform must integrate with GitHub for source control
- Users can view deployment logs in real-time
- System must send notifications on deployment completion
- Support rollback to previous versions

**Focus**: WHAT features the platform provides

---

## Non-Functional Requirements (NFRs)

**What are they?**
- Quality attributes and constraints
- Not about WHAT the system does, but HOW WELL it does it
- Critical for platform success

---


**Key Categories:**
- <span class="emoji">⚡</span> **Performance** - Response times, throughput
- <span class="emoji">📈</span> **Scalability** - Handle growth
- <span class="emoji">🔐</span> **Security** - Authentication, encryption
- <span class="emoji">🛡️</span> **Reliability** - Uptime, disaster recovery


---

## What is the "Cloud"?

---
# The Ultimate Platform

**Cloud computing**  allows us to provision complex pyhiscal infrastructure "virtually"

What do I mean by **"cloud vendors offer the ultimate platform?"**

--- 

## Azure Example

![w:450 h:450](azure.png)

---

**Key Benefits:**
- <span class="emoji">🚀</span> **Scalability** - Scale resources up or down instantly
- <span class="emoji">💰</span> **Cost Efficiency** - Pay only for what you use
- <span class="emoji">🌍</span> **Global Reach** - Deploy anywhere in the world
- <span class="emoji">⚡</span> **Speed & Agility** - Provision resources in minutes

---

## Cautions

- Security and Privacy
- Cost concerns
- Vendor lock-in
- Ownership and control
- Compatibility


---

## Cloud Deployment Models
--- 

### ☁️ **Public Cloud**
- Infrastructure owned by cloud provider
- Resources shared across multiple organizations
- Examples: AWS, Azure, GCP
- **Best for**: Previously mentioned key benefits!

---


### 🏢 **Private Cloud**
- Dedicated infrastructure for single organization
- Greater control and security
- Can be on-premises or hosted
- **Best for**: Regulated industries, sensitive data
---


### 🔀 **Hybrid Cloud**
- Combination of public and private clouds
- Data and applications can move between environments
- **Best for**: Flexibility, compliance requirements, gradual migration

---

## Major Cloud Vendors

### <span class="emoji">☁️</span> **Amazon Web Services (AWS)**
- Market leader, launched 2006
- 200+ services, largest market share


### <span class="emoji">☁️</span> **Microsoft Azure**
- Enterprise-focused, excellent Microsoft integration
- Strong hybrid cloud capabilities

---

## Major Cloud Vendors

### <span class="emoji">☁️</span> **Google Cloud Platform (GCP)**
- Data analytics and ML expertise
- Strong Kubernetes support (created K8s)

### <span class="emoji">☁️</span> **Others**
- IBM Cloud, Oracle Cloud, Alibaba Cloud
- Digital Ocean, Linode (simpler, developer-focused)


---

## Putting It All Together

**Platform Engineering Workflow:**

1. <span class="green-text">**Define Requirements**</span> - NFRs, business needs
2. <span class="green-text">**Design**</span> - Architecture, components, implementation
3. <span class="green-text">**Build**</span> - Implement the requirements
4. <span class="green-text">**Document**</span> - ADRs, guides, runbooks
5. <span class="green-text">**Iterate**</span> - Continuous improvement