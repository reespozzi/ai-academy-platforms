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
  
  .emoji {
    font-size: 1.5rem;
    margin-right: 0.8rem;
    display: inline-block;
    vertical-align: middle;
  }
  
  strong {
    color: #2E8B57;
    font-weight: 600;
  }

header: 'Observability & Monitoring | Kainos'
footer: 'AI-Native Academy 2025'
---

# Observability & Monitoring
## <span class="highlight">See Everything, Know Everything</span>

---

## Where We Are Now

- **Container Apps** running on Azure with your frontend and backend
- May have applications deployed in **Virtual Networks** with proper isolation
- **CI/CD pipelines** automatically building and deploying
- **Infrastructure as Code** with Terraform managing everything
- **Secrets** secured in Azure Key Vault

---

### **How Do You Know If It's All Working?**

> Your Container Apps are deployed. But are they healthy? Are users happy? When things break, can you figure out why? What's happening inside those containers?

---

## Why Observability Matters

**Last week:** More simple to debug, local logs and quick small changes to fix things

---

**Now** Complex to understand, cloud architecture that takes time to deploy small changes, with several moving parts, access levels, reliance on cloud providers, etc etc etc.

> **When something breaks, where do you even start looking? How do you see inside those containers?**

---

**Without observability:**
- "Something's broken, but we don't know what"
- Hours spent guessing where the problem is
- Customers report issues before you know about them
- Fixing one thing breaks something else

----


## The Three Pillars of Observability

### **Metrics**

### **Logs**

### **Traces**

---

### **Health Checks: Is My Container App Alive?**

**Container Apps uses health checks to know if your app is working**

Every Container App should have health check endpoints. Azure uses these to:
- Know when your app is ready to receive traffic
- Detect when your app has crashed
- Automatically restart unhealthy containers
- Route traffic away from failing replicas

---

### **Structured Logging will save you at 2AM**

**Bad logging:**
```javascript
console.log("User login failed");
```

**Good logging**
```javascript
logger.error("User authentication failed", {
  event: "login_failed",
  user_id: userId,
  ip_address: req.ip,
  error_code: "INVALID_CREDENTIALS",
  timestamp: new Date().toISOString(),
  containerRevision: process.env.CONTAINER_APP_REVISION,
  replica: process.env.CONTAINER_APP_REPLICA_NAME
});
```
---

## Alerting

### **The Golden Rule: Alert on What Matters**

**Good alerts:**
- Tell you when customers are affected
- Give you time to fix things before they get worse
- Include enough information to start investigating

---

**What to monitor in every application:**

| Signal | What it means | Container App Alert Example |
|--------|---------------|------------------------------|
| **Latency** | How fast responses are | "Response time > 500ms" |
| **Traffic** | How many requests | "Traffic dropped 50%" |
| **Errors** | How many things are failing | "Container restart rate high" |
| **Saturation** | How full your resources are | "CPU > 80% for 5 minutes" |
| **Availability** | Is the service up? | "Zero healthy replicas" |

> **If you monitor these five things, you'll catch most problems**

---

**Start with the basics:**
- Health check endpoints in all your applications
- Structured logging with correlation IDs
- Simple metrics dashboard
- Basic alerts for service down/high error rate