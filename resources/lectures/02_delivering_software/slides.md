## Content

* Delivering software
  * Anti-patterns
  * Deployment pipeline / Service delivery platform
* Continuous improvement
* Build phase
  * Handling libraries and own components
  * Handling dependencies
* Deployment phase
  * Manage application configuration
  * Handling semi-completed code
* Giving a overview of coming lectures

Note: Tralla


---
## Delivering software

* Lots of focus on the development effort
  * Design, development, testing
  * Only a part of the whole "value stream"
* Getting the software from development to release
  * Hard to learn in courses...
  * Many aspects: release management, coordination, security


--
## Release processes

* Serial or waterfall
  * Ready for release when all functionality has been developed
* Agile
  * Ready for release throughout development
    * Traditional agile believe this should be done at periodic intervals
* Continuous Delivery
  * Subset of agile, Software ready for release at ALL time.
    * Not making a special effort to create a releasable build  
    * Making software ready for release is NOT a separate activity
  * Does not mean releasing into production all the time  



![release](./images/release.png)

Note: Release to manufacturing (RTM), going gold
<br>
Testing first in alpha, holding the version longer. how about changes?<br>


--
## Anti-patterns when deploy
* Deploying manually
  * Human errors, bottle necks
  * Not reproducible
    * Unpredictable, no confident in the service/code
  * Different environments (dev, test, production)
* Deployment comes in late in the process
  * Bugs is found late
  * Gap between dev and ops
    * Devs may not have ops skills (policies)
  * Incorrect assumptions built into system
* Manual configuration management of production environments
  * Configuration drifts, snowflake servers and so on

Note: caching in local vs. cluster


--
## What we seek

* Automated
  * Avoid errors, more confidence
    * Repeatable, reliable, predictable process
  * Self-documented
  * Faster, automate almost everything
* Support frequent changes
  * Smaller changes, fewer roll-backs
  * Fast feedback process
    * Changes trigger a feedback process
    * Code, configuration, host environments, structure of the data
* Bring the pain forward
  * if it hurts, do it more frequently


--
## What we seek

* Build quality in
  * Testing is not a phase, it is everywhere
  * Testing is done by everyone
* Every commit is a release
  * Nothing is 80% done
* Everyone is responsible for the delivery process
  * You built it, you run it
* Everyone is responsible for improvement    


--
## Inspired by lean
* Lean principles are derived from the Japanese manufacturing industry.
  * Studies of Toyota, John Krafcik, 1988
    * "Triumph of the Lean Production System"
    * built in high-quality, faster-to-market
* From lean manufacturing principles
  * Eliminate Waste / Create noting but value
  * Amplify learning - Fast feedback
  * Decide as late as possible for irreversible actions
  * Deliver as fast as possible
  * Respect people - Empower the team
  * Build integrity in
  * Optimize the whole value stream - Continuous improvement

https://en.wikipedia.org/wiki/Lean_software_development




---
## Deployment pipeline

> Every change of code, configuration, environment, data structure and so on triggers the creation of a new instance of the pipeline

![pipeline](./images/pipe02.png) 

Every check-in/commit leads to potential release


--
## Service Delivery Platform (SDP)

* Different cases, different looking pipelines
* Bringing developer creativity to the customer
* Build phase
  * Make installable packages
* Deploy phase
  * Putting it on servers
* The SDP is not just for delivering software 
  * Confidence so that we can innovate
    * Continuous experimenting
  


--
## Service Delivery Platform (SDP)

<img src="./images/sdp.png" width="45%" />

Source: The practice of cloud system administration - 0-321-94318-X
<!-- {_style="font-size: 40%"} -->



--
## Continuous Improvement
* Data-driven deployment
  * Collect metrics for improve the pipeline
  * "Practice makes perfect"
  * Bug lead time
    * Time from bug report to production fix
  * Code lead time
    * From keyboard/code to production
  * Patch lead time
    * From vendor patch to production
  * Frequency of deployment
    * Deployments per time (day/month)
  * Time to restore service
    * Downtime
  * Changes success rate
    * Successful production deployments



---
## Build phase
* Coding 
* Commit 
  * Gate - Pre-submit check
    * Lint, style guide, some tests
* Build 
  * Source code become artifacts
    * Gate - Unit testing
    * Compiling to executables, making packages, processing images
    * Extracting documentation from source code
* Package 
  * Single file that encodes all files to be installed
    * zip, tar + installation script  
* Register
  * Upload the packages to the package registry



--
## Tools in the build phase
* CI servers
  * Hudson, Jenkins, TravisCI, Cruise Control, Strider CD, Circle CI...
    * Uses plug-ins
* Package managers
  * npm, yarn, compose, NuGet, archive managers...
* VCS
  * Git, subversion...


--
## Managing dependencies in build phase
* Third party libraries/packages/modules, compiled or interpreted
  * Store all libraries locally? Download when needed?
    * Guarantee exact versions (deep dependencies - package-lock.json)?
    * Rarely updated
* Own components/packages/modules
  * Build entire app at once on change?
  * Build only the needed component on change?
    * Dependency graph


--
## Dependency graphs

> What to rebuild on a component change?

![deph graph](./images/dep_graph.png)

```
change B => B + D will rebuild
change C => C + D will rebuild
change A => B + C will rebuild then D will rebuild
```


--
## Multiple pipelines

* Splitting up to different pipelines 
  * Different parts have different life cycles
    * Include os kernel + application 
    * Some components are very stable and don´t change 
  * The pipeline becomes to big, to slow
  * Different teams, micro services



![integration pipeline](./images/integration_pipeline.png)



---
## Deployment phase

> Creates the service in one or more testing and production environments


--
## Deployment phase - Promotion
* Promotion - Select versions for release
* Different package repository systems work different
* Tagging
  * Package A - 1.1, 1.2, 1.3(production tag)
  * Package B - 1.4.1, 1.4.2(production tag), 1.4.3
  * Package C - 4.1, 4.2(production tag)
    * Marked as production versions 
* Pinning 
  * package-lock.json (npm shrinkwrap)
  * Pinning the exact versions used for a release
* Test and dev may always use latest


--
## Deployment phase
* Installation
  * pre-install scripts
  * post-install scripts
* Configuration
  * Configuration management
  * Convergent orchestration
    * Always a desire state
  * Direct orchestration
    * multistep to achieve desire goal


---
## Testing
* Gates in the pipeline
  * unit test, integration test/system test, health checks
* Automatic and/or manual approval
* Artifact after test approval 
  * Production/release candidate
    * When a change is safe to put in production



---
## Managing software configuration
* Treat your application configuration as code
* How flexible should configuration be?
* Where in the process to add configuration
  * Build time?
  * packaging time?
  * deployment time
  * startup and runtime?
* Keep configuration in same repo as source code
  * keep the values somewhere else
    * Configuration repository
  * different values depending on app, version env.
* Think about code quality
  * Good naming, DRY, KISS


--- 

## Handle changes 
* How to make changes?
* How to handle semi-completed code?
  * Feature hiding
  * Feature toggling
  * Branch by abstraction
  


-- 
## Branch by abstraction

<div>
* Build an abstraction over the part to change
* Refactor the system to use this abstraction
* Create the change (new part), use feature hiding/toggling to keep it out of production
* Update the abstraction to point to the new implementation
* Remove the old implementation (and abstraction layer if needed) 
</div>
<!-- {_style="font-size: 80%"} -->

![branch by abstraction](./images/branch_by_abstraction.png)


---
## Reading

> Chapter 1, 2 and 13 in the Continuous Delivery book by Humble and Farley

> Next time, Continuous Integration 