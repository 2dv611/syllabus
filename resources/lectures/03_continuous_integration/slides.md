## Content

* Continuous Integration
  * Definition (again)
* Branching


---
## Definitions of CI

* Keep the software at working state all the time
* Regular integration of code base
* 1999, Kent Beck, "extreme programming explained"
* Without CI
  * Software is broken until proven it works
* With CI
  * Software works until it broken
* VCS, Automated builds (CI -server), Agreement of the team

--

## Practices

* Check in regularly
  * A couple of times per day
  * This means smaller changes
    * Less chance of breaking the build
    * Refactor discipline, preserve behavior of the software
    * regular breaks from coding, avoid tunnel vision
  * Fix broken build fast
  * Working with feature branches?
    * Branches != CI?
    * Long-lived branches will have integration problems
    

--
## Practices
* Don´t check in on a broken build
  * Priority to fix broken build
* Run tests both at the developer and in the CI server
  * Update from CSV
  * Run tests and build
  * Commit - Push
* The one that check in must monitor the build process
  * Should not start new work until build is OK
  * No lunch, Don´t go home
* Be prepared to revert
  * Can´t fix the problem in 10 minutes - revert
  * Don´t comment out the tests
* Fail on warnings? - Code quality?
  * Code coverage limit?
  * Number of ToDos
* Have a Build master?
  * Rotating role in big teams
  * When introducing the pipeline

--
## About testing in the pipeline
* Test pyramid

* Keep it fast, keep it short
  * If it take to long time people will ignore it
  * Risk of getting multiple commits in the pipeline
  


---
## CI - software
* Long-running process
  * Execute workflows at regular intervals
  * Polls the CSV
  * Pulls on triggers
* A view of the build and test result
  * Everyone should see the status
    * test coverage, performance, analyses
    * green/red - integration with physical things


--
## Artifact repository

* Most modern CI servers have built-in support for some kind of artifact repository

--
## CI servers

* Jenkins
  * Open source, JAVA, 
  * Flexible with lots and lots of plugin 
  * Web UI 
  * Forked from Hudson 2011 (Oracle claimed the name)

![jenkins screenshot](./images/jenkins.png)


--
## CI servers

* Travis CI
  * SAAS, https://travis-ci.org/travis
  * Build and test projects on GitHub
  * travis.yml - root at the repository
  * Free for open source projects
  
![travis screenshot](./images/travis.png)

--
## CI servers

* Go CD
  * ThoughtWorks company
  * Free of charge, support costs
  * Include the concepts of more complex pipelines

![Go CD screenshot](./images/gocd.png)

--
## CI servers

* Others
  * TeamCity
    * JetBrain, Mature, enterprise, best .NET support
  * Bamboo
    * Atlassian, JIRA and Bitbucket, Also as cloud service
  * CircleCI
    * Cloud service, GitHub, Docker support, Fast and cheap
  * CodeShip
    * Cloud service, Pro versions have Docker support

Source: https://www.code-maze.com/top-8-continuous-integration-tools/
<!-- {_style="font-size: 40%"} -->


--
## Short demo

> Setting up a node.js "Hello world" on Jenkins

---
## How to work in your pipeline?

> Always releasable - How?


--
## feature branch


## The commit step

![image of commit step](./image/commit_step.png)
  


--

---
## Reading

> Chapter 3, 5, 7 and 14 in the Continuous Delivery book by Humble and Farley
