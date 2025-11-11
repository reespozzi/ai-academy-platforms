# So you finished early

## Objective

Build something awesome, keeping in mind all the high level content that we covered. How might you make the developer experience better if you had to hand this off to a team? How might you improve the security posture or time to production?

This is your chance to build value adds and show off at the end, if you get round to it!

---

## Prerequisites

- Your 3-Tier application running in Azure, in more than one environment.

---

## Potential things to look at

- Separate repo for GitHub Actions templates? D.R.Y principles!
- Try to get working with persistent cloud database instead?
- Security scanning in pipeline?
- You have dev and prod, can you add another environment?
  - Can you run a test suite against the deployed service?
- How do you know if your service has gone down? Can you add a delayed app breaker and detect it?
- Can you move your container app into a terraform module and use it for frontend and backend?
- Build and deploy your own app? Maybe another microservice to fetch and compare market rates for jobs? Get used to docker and terraform workflow
- Ask Copilot! In the real world we do not build to a spec in this way, we have to gather requirements, and find something that fits. What else makes sense to add to your deployments and pipelines?
- What else is [best practice?](https://learn.microsoft.com/en-gb/azure/well-architected/)
  - https://learn.microsoft.com/en-gb/azure/well-architected/service-guides/azure-container-apps
