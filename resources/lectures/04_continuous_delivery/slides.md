## Content

* Deploying and Releasing Applications
* Managing Data
* Managing Continuous Delivery


---
## Deploying and Releasing Applications
* Release Strategy
  - who is in charge of deployments to each environment
  - asset and configuration management strategy
  - which technology should be used for deployment
  - plan for implementing the deployment pipeline
  - which test environments should be available for:
    - acceptance
    - capacity
    - integration
    - user acceptance
  - requirements for monitoring the application

Note:
Meeting with all stackholders to discus deployment and maintenance of the application throughout its lifecycle


--
## Deploying and Releasing Applications
* Release Strategy
  - description of the integration with any external systems
    - at what stage and how are they tested
    - communication with the provider in the event of a problem
  - disaster recovery plan
  - service-level agreements for the software
    - failover and other high-availability strategies
  - production sizing and capacity planning
  - archiving strategy
  - initial deployment to production
  - how fixing defects and applying patches to the production environment
  - how upgrades to the production environment will be handled

Note:
**Production sizing and capacity planning**<br />
How much data will your live application create?<br />
How many log files or databases will you need?<br />
How much bandwidth and disk space will you need?<br />
What latency are clients expecting?<br />


--
## The Release Plan
A document that describes how to:
* release the application för the first time
* smoke-test the application
* back out if something go wrong during the deployment
* back up and restore the application’s state
* update the application without destroying the application’s state
* rollback if somethings go wrong
* monitoring the application
* log problems from previous deployments, and their solutions


--
## The first deplyment
> “The first deployment of any application should happen in the first iteration when you showcase your first stories or requirements to the customer.”<!-- {_style="font-size: 75%"} -->

After this first iteration, you should have the following in place:
* Your deployment pipeline’s commit stage
* A production-like environment to deploy to
* An automated process that takes the binaries created by your commit stage and deploys them into the environment
* A simple smoke test that verifies that the deployment worked

Note: 
“How different is the production environment from my development environment?”


---
## Reading

> Chapter 10, 12, 15 in the Continuous Delivery book by Humble and Farley
