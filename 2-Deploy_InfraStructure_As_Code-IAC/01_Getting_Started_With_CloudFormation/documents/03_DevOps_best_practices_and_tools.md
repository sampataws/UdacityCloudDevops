#DevOps best practices and tools
One of the benefits of using DevOps is that it allows predictable deployments using automated scripts. In the DevOps model, development and operations teams are merged into a single team. These DevOps teams use a few tools and best practices that deploy and manage configuration changes to servers. [Stackexchange](https://softwareengineering.stackexchange.com/questions/130850/difference-between-devops-and-software-configuration-management) has a discussion post detailing the difference between DevOps tools vs. Software Configuration Tools.

The most important practices are:

* **Continuous Integration / Continuous Delivery (CI/CD)** - new features are automatically deployed with all the required dependencies.
* **Infrastructure as Code (IaaC)** - configuration and management of cloud infrastructure using re-usable scripts.

Other prevalent practices are:

* Microservices
* Monitoring and Logging
* Communication and Collaboration

##Glossary
1. **Continuous Integration Continuous Deployment (CI/CD)**: Tracks the development workflow from testing through production. Continuous integration is the process flow of testing any change made to your development flow, while continuous deployment tracks those changes through to staging and production systems. You may like to read this article by [Atlassian.com](https://www.atlassian.com/continuous-delivery/principles/continuous-integration-vs-delivery-vs-deployment) that describes CI/CD in detail.

2. **Infrastructure as code (IaaC)**: Provision and manages the cloud-infrastructure by using scripts. These scripts can be written in YAML or JSON format. These scripts ensure that the same architecture can be re-built multiple numbers of times. These scripts are particularly useful in enterprise applications and different environments - dev, prod, or test. Read more [here](https://en.wikipedia.org/wiki/Infrastructure_as_code).