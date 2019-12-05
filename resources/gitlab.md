## About this document
This is a short article written for the course 2dv611 at Linneaus University, Kalmar regarding the use of GitLab CI. The article do not aim for a full coverage of the area but will give some guidelines to the project done in the course.

## About GitLab
The GitLab project started out as a small open-source project but has grown to be one of the most popular VCS and CI-server solution. GitLab is available in two versions, one free Community Edition (CE) and one Enterprise Edition (EE). You could also use the service as a SaaS-variant by creating an account at [gitlab.com](gitlab.com). 

Gitlab itself is not a monolithic application. It contains different core components that have different responsibilities. Most of the components started as Ruby on Rails-components, but the later ones have been written in Go.

### Installing Gitlab
If you consider to install your own instance of Gitlab instead of using the SaaS-application the recommended way is to use the Omnibus package that, with help by included Chef-scripts, handling all of the different core components installation. You find the instructions how to do this installation here: https://about.gitlab.com/install/. I would recommend installing it on a dedicated instance/virtual machine that have at least 8GB RAM. The installation process should be pretty forward and you should be able to create user accounts and projects for these users. The project is like a repository in Github and you will have to configure it likewise; like adding SSH-key etc.


### Building pipeline
The main thing in this course is to build an effective and friction-free pipeline as possible that also will support a professional way of working in a team of developers on same code base. The heart of this flow is the pipeline defined in the file gitlab-ci.yml (placed in the repo:s root). This is as you can see below an YAML-file that defines the different stages and jobs your Gitlab CI pipeline should do. You find the documentation for this file here: https://docs.gitlab.com/ee/ci/yaml/README.html. As you will see it have a lot of different parameters to work with to optimize your pipeline just as you want it. Be sure to study the options you have. For more information see the documentation: https://docs.gitlab.com/ee/ci/yaml/README.html#configuration-parameters

In this file you define stages that could include jobs. A job is something you do in the pipeline, that often requires some kind of scripting or commando. If we look at an example:

```yaml
# if no docker image is defined use this
image: "node:alpine"

# You could add variables here
variables:
  IMAGE_NAME: calculator

stages:
  - commit
  - build
  - staging
  - production

lint:
  stage: commit
  script:
    - npm ci
    - npm run lint

unit_test:
  stage: commit
  script:
    - npm ci
    - npm test

build_image:
  stage: build
  image: docker:18.09
  variables:
    DOCKER_DRIVER: overlay2
  services:
    - docker:18.09-dind
  before_script:
    - echo "do som login stuff to registry"
  script:
    - echo 'build, tag and push image here'

integration_test:
  stage: staging
  script:
    - echo 'Run integration test'


deploy:
  stage: production
  when: manual  # This is a manual gate
  script:
    - echo 'code that deploy here'

```

As you probably can figure out the pipeline have four steps; commit, build, staging and production. Each stage have one or more jobs that is described as the actual work the pipeline does. In this case you could run shell commands.

### Gitlab runners
All jobs that a pipeline is doing runs on a service called GitLab Runners. This is a separate service that is used by a Gitlab project just for running jobs, doing the work a pipeline has defined. That means that the commands or script defined is not run on the GitLab server. A runner could be shared by other project or could be dedicated to a single project or even a specific job. If you run a own instance of Gitlab CI-server you have the freedom of having dedicated runner(s). If you run Gitlab CI as a SaaS you probably have to share runners with other projects which could mean delays if many are running simultaneous jobs. 

When installing a runner there are several ways of doing that. More information: https://docs.gitlab.com/runner/. In the web UI of Gitlab you have the ability to connect your Kubernetes Cluster and directly install a github runner as a pod in the cluster (must be logged in as an admin). That is an easy way but may have some security concerns and it is hard to configure the runner the way you probably need. This way is also just tested and guarantee to work on the big public cloud providers. 

Another way is to make a more manual installation in your cluster using [Helm](https://helm.sh/). Helm is a kind of manager for deploying and handling applications in a Kubernetes cluster (could be a good stuff to look up for deploying your application). When using this way you have the ability to configure some configuration values in a file called values.yaml. A third way is to install the runner on a own instance/virtual machine. There are also ways to scale more runners if needed.

One thing to remember is that after you install your runner you must register it. More information: https://docs.gitlab.com/runner/register/index.html

### Docker
As you could see in the gitlab-ci.yml file above we use the image:-directive to use Docker images for building the software. We have full support for using Docker and Gitlab will help with pulling the images down from Docker hub or a private registry or use the Gitlab Container registry (https://docs.gitlab.com/ee/user/packages/container_registry/). 

There is also a default image provided for building the application artifacts. In this case it is a node:alpine from Docker Hub. When running your pipeline you have put the gitlab-ci.yml and probably a Dockerfile in the root folder of your repository meaning that the pipeline:s script easy can build the image(s) and embed the current source-code when triggered. You can build the images, run the tests and if successful push the image (tagged) to your image registry.

Many time when you work with scripts in your pipeline you want to use environment variables. There are some pre-defined variable in Gitlab you could use. You find these: https://docs.gitlab.com/ce/ci/variables/predefined_variables.html (CE). You also have the ability to add your own variables in your project. You can mask and protect these variables and then use in your pipeline-file. To learn how read the docs: https://docs.gitlab.com/ee/ci/variables/README.html

### Deploy to Kubernetes
You have two Kubernetes clusters on cscloud. You are free to use them as you want (or if you use a public cloud provider). For staging and production, or one for just playing around and then using Kubernetes namespaces in the other. When deploying applications to your cluster there are some thing to think about. How do we get the runner to deploy to our cluster since it is an own instance? Should you give the runner the credentials and the tools to deploy on k8s? What if the runner is shared by other projects and people?

How will we deploy with a thought on scalability? Load balancing? State sharing? How do we roll-back a deployment? Could we use techniques like canary release?
Maybe could Helm (described above) be a tool that help us?

## Other things to think about
Here are some problems that also should be considered.

#### How will the developer work locally?
The developers are the most important stakeholder in this project. The focus of the project is to make the life of a programmer in your product team as easy as possible. The developer must have the fleability to run her/his own tools and have the ability to test new features or bug fixes in a production like environment to avoid simple mistakes that break the builds. How will you do that? How should the developers setup look like? Docker-compose? Minicube? Could you provide easy set-up script for a new developer. How is the documentation for newly arrived developers. As soon as possible a new developer can deliver the better! The developers must feel that they are not fighting against the tools, and the the workflow is easy and friction-free.

#### Organizing images
Since we be using Docker images and we build a lot of images we must keep them organized in a automated way. We need to track images back to the right commit and we need to know what images are used in a testing environment and what images are the current productio. You need to find (and document) a system for tagging (and re-tagging) your images in the pipeline. You probably could use some of Gitlabs environment variables for this. Also think about how we handle this if a build that fails. We probably also need some clean-up?

### The pipeline must support the workflow
What type of git workflow do we use? Git-flow? Github-flow? Gitlab-flow? (https://medium.com/@patrickporto/4-branching-workflows-for-git-30d0aaee7bf). The pipeline must support this and keep it flexible and useful for the developers. When do we need to build images? On every commit in ever branch? Only on merge request to master? Or something in between?  

### Configuration and security
How do we handle credentials in a secure way? How do we deploy our application in a secure way? Password complexity? Security in the cluster? To our image registry?
Also think about the configuration. How do we run the application in a test environment and how do we do it in production.
  




