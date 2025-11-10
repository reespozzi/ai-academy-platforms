# AI Academy Platforms 2025

Learning for select **Platform Engineering** concepts, practices, and hands-on implementation using modern cloud-native technologies.


This repository contains a structured learning path to take you from containerization basics to building platform engineering solutions on Azure.

It focusses on Docker, Terraform and Azure, using GitHub Actions.

## Structure

### [Introduction](intro/) - Platform Engineering Fundamentals
- What is Platform Engineering and why it matters
- Core principles: Developer Self-Service, Golden Paths, DevEx
- High-Level Design (HLD), Low-Level Design (LLD), and Requirements
- Understanding cloud computing and major vendors

### [Part 1: Containerization](part-1/) - Building Blocks
- **Concepts**: Docker fundamentals, containers vs VMs, registries
- **Tasks**: 
  - Build Docker images for applications
  - Optimize image size and security
  - Push to Azure Container Registry
  - Implement proper image versioning strategies

### [Part 2: Infrastructure as Code](part-2/) - Automated Infrastructure
- **Concepts**: Terraform basics, state management, modules
- **Tasks**:
  - Create first Terraform deployment
  - Implement remote state and modules
  - Learn deployment options (ACI, App Service, Container Apps, AKS)

### [Part 3: CI/CD Automation](part-3/) - Continuous Delivery
- **Concepts**: CI/CD principles, GitHub Actions, pipeline security
- **Tasks**:
  - Build first CI pipeline with automated testing
  - Create CD pipeline with conditional deployments
  - Integrate container registry and infrastructure automation

### [Part 4: Azure Platform](part-4/) - Cloud-Native Architecture
- **Concepts**: Azure networking, security (IAM, NSGs), PaaS vs IaaS
- **Tasks**:
  - Deploy Container Apps with Terraform
  - Configure virtual networks and subnets
  - Connect isolated VNets with peering
  - Stretch goals for advanced implementations

### [Part 5: Observability](part-5/) - Monitoring & Operations
- **Concepts**: Three pillars of observability (metrics, logs, traces)
- Monitoring strategies, alerting, and health checks
- Structured logging and correlation

### [Stretch Goals](part-4/) - Make it awesome
- Add value to your solution
- Add as much as you can to make this "production ready" in the time you have

### [Demo](demo/) - Showcase Your Work
- Presentation guidelines and demo day preparation
- Documentation standards for production handoff

## Technologies Covered

- **Containerization**: Docker, Azure Container Registry
- **Infrastructure**: Terraform, Azure (Container Apps, VNets, Key Vault), RBAC, Azure Entra
- **CI/CD**: GitHub Actions, automated testing and deployment
- **Security**: Azure IAM, Service Principals, Managed Identities, Azure Key Vault
- **Monitoring**: Azure monitoring, structured logging, health checks

## Prerequisites

- Basic understanding of web applications
- Git and GitHub familiarity
- Docker Desktop installed
- Azure subscription access
- Terraform installed
- VS Code with recommended extensions

## 🎓 Learning Outcomes

By completing this curriculum, you will:

- Build and optimize containerized applications
- Implement Infrastructure as Code with Terraform
- Create automated CI/CD pipelines
- Design secure, scalable cloud architectures
- Apply observability and monitoring best practices
- Present technical solutions effectively
- Have something running in the cloud!