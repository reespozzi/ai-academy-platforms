# So you finished early

## Objective

Build something awesome, keeping in mind all the high level content that we covered. How might you make the developer experience better if you had to hand this off to a team? How might you improve the security posture or time to production?

This is your chance to build value adds and show off at the end, if you get round to it!

---

## Prerequisites

- Your 3-Tier application running in Azure, in more than one environment.

---

## Potential things to look at in no particular order

- Try to get working with persistent cloud database instead?


- What else is [best practice?](https://learn.microsoft.com/en-gb/azure/well-architected/)
  - https://learn.microsoft.com/en-gb/azure/well-architected/service-guides/azure-container-apps


- Security scanning in pipeline?

- Separate repo for GitHub Actions templates? D.R.Y principles!

- Can you move your container app into a terraform module and use it for frontend and backend?

- Auto-Shutdown functionality? How can we turn this off overnight, and have it turn back on in the morning? Saves money!
- Tagging terraform module?
  - builtFrom (which repo?)
  - teamName
  - environment
- Container Images cleanup (older than 48H and not the latest (not latest tag) version
- You have dev and prod, can you add another environment?
  - Can you run a test suite against the deployed service?
- How do you know if your service has gone down? Can you add a delayed app breaker and detect it?
- tfcmt?
- Can you get a nice monitoring dashboard with Grafana?
- Build and deploy your own app? Maybe another microservice to fetch and compare market rates for jobs? Get used to docker and terraform workflow
- Ask Copilot! In the real world we do not build to a spec in this way, we have to gather requirements, and find something that fits. What else makes sense to add to your deployments and pipelines?
- Can you take another service from Well-Architected and build from scratch?
