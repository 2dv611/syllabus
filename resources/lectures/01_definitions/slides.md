## Content

* The idea behind this course
  * What this course focus on 
  * What we expect you to know
* Definitions used in this course
* ~~The examination assignment~~

Note: Tralla


---
## Why this course?

* Focus on delivering software to production
* Building deployment pipelines
* Prepare for thesis?
* Prepare for working with software...with other people
  * There will be some coding...


--
## What we expect you to know

* Testing
  * Unit, acceptance, integration, non-functional
  * Writing and implement
* Working with Git
  * We will focus on using git in groups
* Writing code
* Familiar to Docker and Kubernetes
  * Provisioning servers, containers...
* Taking responsibility for your own learning
  * want to learn...

Note: How to write test, when to use them, different kinds and so on.


---
### Some definitions

* Service delivery platform
  * The platform for delivering software eg. deployment pipeline 
  * Validates after every stage in the pipeline (commit, acceptance, staging, production) 
* Service delivery flow 
  * The flow from the beginning to the end
  * Both automatic and manual approvals depending on the step
* Gate
  * A condition for going further in the flow. 

![pipeline](./images/pipe02.png)


---
## Some more definitions
* Artifacts 
  * Products produced during the development of software
* Software package
  * During the build step
  * A container or single file that contains every thing to install the application, patch or library
* Package repository
  * A kind of repository holding produced packages/artifacts
* CI server
  * A software used for building service delivery platforms


--
## Continuous Integration

* Merge code on commit
  * One code repository
  * Find errors early!
  * No integration debts
* Automated builds
  * fast builds
* Automated testing
  * fast test runs
* Commit every day
  * If a commit fails - fix it as fast as possible
* Everyone can see the results of the latest build
  * Transparency




--
## Continuous Delivery

> To have the confidence that the artifact(s) going trough the pipeline will work in production.


--
## Continuous Deployment

> The whole chain from committing a code change to running the change in production is automated


--
## Deployment pipeline

![pipeline](https://github.com/CS-LNU-Learning-Objects/web-application-architecture/raw/master/images/pipeline.png)



--
## What we aim for

* Confidence
* Reduced risk
* Shorter time from keyboard to production
* Less wait time
  * International time spans
* Continuous Improvement
* Job satisfaction



---
## How we will practice this?

* Individual preparation in form of a report
  * Getting the fundamental knowledge
  * Thinking about a real problem
  * Reading other reports from group members
* Group project
  * Setting up the pipeline
  * Working as a group of developer through the pipeline
    * Continuous Improvement!



