# Stretch Task: Explore Alternative Deployment Options

## Objective

**For students performing well:** Challenge yourself to deploy your application to a different Azure service and discover the trade-offs. This is independent exploration work - you'll need to research, experiment, and learn with minimal guidance.

---

## Prerequisites

- Working Container Apps deployment from previous tasks
- Docker image in Azure Container Registry
- Curiosity and willingness to experiment
- GitHub Copilot available for assistance

---

## Your Challenge

### Choose Your Adventure

Pick **one** alternative Azure service to explore (or multiple if you're feeling ambitious):

- **Azure Container Instances (ACI)** - Serverless containers
- **Azure App Service** - Managed platform service
- **Azure Web Apps** - Traditional web hosting platform
- **Azure Functions** - Serverless compute (if you can adapt your app)
- **Azure Kubernetes Service (AKS)** - Full Kubernetes (advanced)
- **Azure Static Web Apps** - For frontend apps with API backends

### Your Mission

**Get your application deployed and running on your chosen service.** That's it. No step-by-step instructions, no detailed guidance - figure it out!

### Research Phase

Before you start deploying, spend time understanding:
- What is this service designed for?
- How does it differ from Container Apps?
- What are the key concepts and terminology?
- What are the pricing implications?

**Use Copilot to help you understand the service and generate deployment scripts/configurations.**

### Deployment Phase

Your goal: Get your application accessible via a public URL on your chosen service.

**Expect to encounter:**
- Configuration challenges
- Service-specific limitations
- New concepts to learn
- Multiple attempts before success

**Resources to leverage:**
- Azure documentation
- GitHub Copilot for commands and configurations
- Azure CLI help
- Azure portal exploration

### Documentation Phase

Document your journey:
- What service did you choose and why?
- What was the most challenging part?
- How does it compare to Container Apps?
- What would make you choose this service in a real project?
- What did you learn about Azure's ecosystem?

---

## Success Criteria

**Minimum viable completion:**
✅ Application successfully deployed to alternative service  
✅ Application accessible via public URL  
✅ Can explain key differences from Container Apps  

**Stretch goals:**
✅ Deployed to multiple alternative services  
✅ Configured custom monitoring/logging  
✅ Set up custom domain (if supported)  
✅ Explored scaling options  
✅ Analyzed cost implications  

---

## Reflection Questions

After your exploration:

1. **What was the biggest "aha!" moment during this task?**

2. **Which service felt most natural to work with? Why?**

3. **If you had to choose between your explored service and Container Apps for a production application, what factors would influence your decision?**

4. **What gaps in your Azure knowledge did this task reveal?**

5. **How confident would you feel recommending your chosen service to a colleague?**

---

## Cleanup

**Important:** Don't forget to clean up your resources when you're done exploring!

Use Copilot to help generate cleanup scripts for whatever services you deployed to.

---

## Extension Challenges

If you're looking for even more challenge:

### Multi-Service Architecture
Deploy different parts of an application to different services:
- Frontend to Static Web Apps
- API to Container Apps
- Background jobs to Container Instances
- Make them work together

### Infrastructure as Code
Try to recreate your deployment using:
- ARM templates
- Bicep
- Terraform
- Azure CLI scripts

### Advanced Configuration
Explore advanced features of your chosen service:
- Custom scaling rules
- Security configurations
- Integration with other Azure services
- Performance optimization

---

## Key Learning Goals

This task is about:
- **Independent problem-solving** in cloud environments
- **Research and exploration** skills
- **Understanding Azure's diverse service offerings**
- **Making technology choices** based on requirements
- **Learning to learn** new cloud services quickly

**Remember:** There's no single "right" answer. The goal is exploration, learning, and building confidence with unfamiliar Azure services!

**Document:**
- URL for each deployment
- Time to first successful request
- Any issues encountered
- User experience differences

---

### Part E: Explore Scaling Capabilities

Understand how each service handles scaling.

**Container Apps:**
- Review auto-scaling rules
- Understand scale-to-zero
- Test HTTP-based scaling

**ACI:**
- Explore manual scaling options
- Understand container groups
- Learn limitations

**App Service:**
- Check scaling options in your plan tier
- Understand auto-scale rules
- Compare with manual scaling

**AI questions:**
- "How does auto-scaling differ between these services?"
- "Which service can scale to zero?"
- "What are the limitations of ACI scaling?"

---

### Part F: Analyze Monitoring and Logging

Compare observability across services.

**For each deployment:**
- Find application logs
- View container logs
- Check metrics availability
- Explore diagnostic settings

**Questions to explore:**
- "How do I view logs for each service?"
- "What metrics are available by default?"
- "Which service has the best monitoring capabilities?"

**Document your findings:**
- Ease of accessing logs
- Richness of metrics
- Integration with Log Analytics
- Alerting capabilities

---

### Part G: Cost Analysis

Understand the pricing model for each service.

**Use Azure Pricing Calculator to estimate:**
- Cost for low traffic (few requests per day)
- Cost for medium traffic (1000 requests per day)
- Cost for high traffic (100,000 requests per day)

**Consider:**
- Fixed vs consumption-based pricing
- Scale-to-zero savings
- Minimum commitments
- Additional features included

**AI prompts:**
- "Explain Azure Container Apps pricing"
- "How is ACI billed?"
- "What's included in App Service Plan pricing?"

---

### Part H: Evaluate Management Experience

Rate the developer experience for each service.

**Consider:**
- Initial setup complexity
- Deployment process
- Configuration options
- Update/rollback process
- Documentation quality
- Portal vs CLI experience

**Create a developer experience rating:**
- Setup difficulty (1-5)
- Deployment ease (1-5)
- Monitoring access (1-5)
- Overall satisfaction (1-5)

---

## Success Criteria

✅ Successfully deployed to all three services  
✅ All deployments are accessible and working  
✅ Created comprehensive comparison matrix  
✅ Tested scaling capabilities  
✅ Analyzed cost differences  
✅ Evaluated developer experience  
✅ Can articulate when to use each service

---

## Discussion Points

After completing the task, be ready to discuss:

1. **Which service was easiest to deploy to? Why?**
2. **When would you choose ACI over Container Apps?**
3. **What are the key differences you noticed?**
4. **Which service offers the best value for different scenarios?**
5. **How do the scaling capabilities compare?**
6. **Which would you use for a production application?**
7. **What surprised you about each service?**

---

## Real-World Scenarios

Match each scenario to the best service:

### Scenario 1: Batch Processing Job
**Requirements:** Runs once daily for 30 minutes, processes files, then stops
**Best service:** ?
**Why:** ?

### Scenario 2: Production Web API
**Requirements:** 24/7 availability, variable traffic, needs staging slots
**Best service:** ?
**Why:** ?

### Scenario 3: Microservices Platform
**Requirements:** 10 services, inter-service communication, event-driven scaling
**Best service:** ?
**Why:** ?

### Scenario 4: Development Environment
**Requirements:** Used occasionally by developers, needs to be cost-effective
**Best service:** ?
**Why:** ?

---

## Extension Challenges

### Challenge 1: Multi-Container Deployment
Try deploying a multi-container application:
- Create a simple frontend and backend
- Deploy both containers
- Configure them to communicate

Which service handles this best?

### Challenge 2: Custom Domain
Pick one service and configure a custom domain:
- Learn about DNS configuration
- Understand SSL/TLS certificates
- Test HTTPS access

### Challenge 3: Health Probes
Configure health checks for each service:
- Understand liveness probes
- Set up readiness checks
- Test restart behavior

---

## Comparison Template

Fill this out based on your experience:

### Azure Container Instances
**Pros:**
- 
- 
- 

**Cons:**
- 
- 
- 

**Best for:**
- 

---

### Azure App Service
**Pros:**
- 
- 
- 

**Cons:**
- 
- 
- 

**Best for:**
- 

---

### Azure Container Apps
**Pros:**
- 
- 
- 

**Cons:**
- 
- 
- 

**Best for:**
- 

---

## Cleanup

**Important:** These deployments cost money!

After completing your comparison:
- Delete ACI container instance
- Delete App Service and Plan
- Decide whether to keep Container Apps for next task
- Keep ACR (needed for future tasks)

**AI can help:**
- "How do I delete an Azure Container Instance?"
- "How do I remove an App Service and its plan?"

---

## Key Learnings

By the end of this task, you should understand:

- ✅ Practical differences between Azure container services
- ✅ When to use each service in real projects
- ✅ Cost implications of different options
- ✅ Trade-offs between simplicity and features
- ✅ How scaling works across services
- ✅ The importance of choosing the right service

---

## Reflection Questions

Document your thoughts:

1. **Which service surprised you most? How?**


2. **Which service would you recommend to a friend starting a new project?**


3. **What factors would make you choose a more complex service?**


4. **How does your choice of service affect your development workflow?**


5. **What did you learn about Azure's approach to container hosting?**

---

## Next Steps

Now that you understand the deployment options:
- You're ready to learn Infrastructure as Code
- Think about how you'd automate these deployments
- Consider how to manage multiple environments
- Prepare to define infrastructure in Terraform!

**Remember:** The best service is the one that matches your needs, not the most advanced one!
