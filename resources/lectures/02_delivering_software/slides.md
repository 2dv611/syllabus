## Content

* Delivering software
  * Anti-pattern
  * Deployment pipeline
    * Build, deploy
* modules/packages


Note: Tralla


---
## Delivering software?

* Lots of focus on the development effort
  * Design, development, testing
  * Then what?
* 


--
## Traditional view

![release](./release.png)

> Delaying testing until after the development


Not: Release to manufacturing (RTM), going gold
<br>
Testing first in alpha, holding the version longer. how about changes?<br>


--
## Deployment pipeline

> Every change of code, configuration, environment and so on triggers the creation of a new instance of the pipeline

![pipeline](./images/pipe02.png) 

Every check-in/commit leads to potential release
---
## Some definitions

> Make every part of the process of building, deploying, testing and releasing the software visible to everyone involved. It also improve feedback and support automation for faster release.

---
## Anti-patterns
* Deploying manually
  * Human errors
  * Take times
  * Bottle necks
  * Not reproducible
  * Different environments
  * Unpredictable, no confident in the service/code
* Late deployment to production environment
  * Bugs late in the process
  * Gap between dev and ops
  * Devs don´t have ops skills (policies)
  * Incorrect assumptions built into system
* Manual configuration management of production Environments
  * Configuration drifts, snowflake servers and so on

Note: caching in local vs. cluster
--
## What goals do we have

* Automated
  * Avoid errors, more confidence
    * Repeatable, reliable, predictable process
  * Self-documented
  * Faster, automate almost everything
* Frequent
  * Smaller changes, fewer roll-backs
  * Fast feedback process
    * code, configuration, host environments, structure of the data
    * Under control so changes trigger a feedback process
* Bring the pain forward
  * if it hurts, do it more frequently
* Build quality in
  * testing is not a phase, it is everywhere
  * testing is done by everyone
* Done means release
  * no 80% done
* Everyone is responsible for the delivery process
* Everyone is responsible for improvement    


--
## Inspired by lean
* Lean principles are derived from the Japanese manufacturing industry.
  * Studies of Toyota, John Krafcik, 1988
    * "Triumph of the Lean Production System"
    * built in high-quality, faster-to-market
* From lean manufacturing principles
* focus on removal of wast and reduction of cost
* Value stream


--
## Service Delivery Platform (SDP)

* Deployment pipeline
* Different cases, different look
* Build and deploy
  * make installable packages
  * Putting it on servers
* The service is not just software 
  * A good SDP take this in count
  * Confidence so that we can innovate
  * Bringing developer creativity to the customer

--
## Service Delivery Platform (SDP)

![sdp](./sdp.png)


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
* Coding step
* Commit step
  * Gate - Pre-submit check
    * Lint, style guide, some tests
    * At the developers
* Build step
  * Source code become artifacts
    * Unit testing
    * Compiling to executables, making packages, processing images
    * Extracting documentation from source code
* Package step
  * Single file that encodes all files to be installed
    * zip, tar + installation script  
    * Runnable in any environments
* Register step
  * Upload the packages to the package registry
--
## Tools in the build phase
* CI servers
  * Hudson, Jenkins, TravisCI, Cruise Control, Strider CD
* Package managers
  * npm, yarn, compose, NuGet, archive programs...
* VCS
  * Git, subversion...


--
## Managing dependencies
* Third part libraries/packages/modules, compiled or interpreted
* Keep local storage of all libraries? Download when needed?
  * Dependencies?
  * Guarantee exact versions (deep dependencies)?
  * Rarely updated
* Own components
  * build entire app at once on change?
  * Build only the changed component on change?
  * Plan for handling dependencies?
    * Circular dependencies?


--
## How to handle the built components
  * Check into repositories
    * Depends on size of project
  * Artifact repository
  * Splitting up to different pipelines
    * Different parts have different life cycles
      * Include os kernel + application
    * Some components are very stable and don´t change
  * The pipeline becomes to big, to slow

  ![integration pipeline](./itegration_pipeline.png)

--
## Dependency graphs
![deph graph](./deph_graph.png)

```
change B => B + D will rebuild
change E => C + D will rebuild
change A => B + D rebuild then D rebuild
```

* Upstream dependencies
  * to the left
* Downstream dependencies
  * to the right
* automated triggers

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

--
## Managing environments


-- 
## Keeping your application releasable
* How to make changes?
  * How to handle semi-completed code?
* Feature hiding/toggling
* Branch by abstraction
  * Building an abstract layer upon the piece that should change


-- 
## Branch by abstraction

1. Build an abstraction over the part to change
2. refactor the system to use this abstraction
3. create the change (new part), use feature hiding/toggling to keep it out of production
4. Update the abstraction to point to the new implementation
5. Remove the old implementation (and abstraction layer if needed) 

![branch by abstraction](./branch_by_abstraction.png)


---
## Deployment phase

> Creates the service in one or more testing and production environments


--
## Deployment phase
* Promotion
  * Package A - 1.1, 1.2, 1.3(production)
  * Package B - 1.4.1, 1.4.2(production), 1.4.3
  * Package C - 4.1, 4.2(production)
    * Marked as production versions (tagging)
    * Test and dev may always use latest
  * Pinning versions
    * package-lock.json (npm shrinkwrap)
    * Pinning the exact versions used for a release
* Installation
  * pre-install scripts
  * post-install scripts
    * smoke tests
* Configuration
  * Configuration management
  * Convergent orchestration
    * Always a desire state
  * Direct orchestration
    * multistep to achieve desire goal

--
## Testing
* Gates in the pipeline
  * unit test, integration test/system test, health checks
* Automatic and/or manual approval
* Artifact after test approval 
  * Production/release candidate
    * When a change is safe to put in production

