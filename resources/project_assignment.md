## Project Assignment - 2DV611

This text will describe the project assignment for the course 2dv611 at Linnaeus University, Kalmar, Sweden.

### A deployment pipeline

The assignment is a group project where you should develop a deployment pipeline supporting a continuous delivery workflow of an open source application.
The application should be an open source web application, which is up to the group to decide based upon the work you did in the reports.

The deployment pipeline should be build for a developer team to continuously develop and maintain a web application.
The goal is to achieve a pipeline where a new developer can continue the development of the application in a transparent, easy and quality way.

This assignment have several parts and learning objectives:

* Getting the understanding for producing deployment pipelines, including adding CI-servers, artifact repositories and so on.
  * The first draft of this will be done in the individual theoretical preparation in the report, then implemented  and improved as a group assignment
* Getting a understanding for how to implement testing of software and application in the deployment pipeline
  * After the individual report assignment is handed in, you will be grouped together and your group will set up the deployment pipeline from the outcomes of the reports
* Working in group with a real software project, The application, using integration techniques in your deployment pipeline
  * Yes, there will be some coding and development, One group, many small commits, try to keep the code ready for production
* Automate deployment in different environment maximizing the feedback speed of errors/bugs and the confidence in the code
  * Proper integration tests, notifications when failing and so on
* Getting the code changes all the way to production
  * Your web application should be running in a production environment as a last step of the deployment pipeline, see production environment for more information.

We will not specify a long list of functional requirement. At this level you should be able to think about the problem and identify wanted features by your self. By reading the literature and article you will get the understanding of the parts implemented in a good deployment pipeline and how to bring your software and code changes to production in a fast, confident and secure way.

We are aiming for continuous Improvement!

To get a better understanding of a more complex software, all project members must be active throughout the development. **Every member of the team should do a lot of commits** and you should use the idea behind continuous integration to get the experience needed.

### Tools at your disposal
To facilitate you in this assignment, we will provide you with a variety of tools and systems.

* 2DV611 organization Github repository - should be used for the examination artifacts and maybe planing
* Production environment in the form of a Kubernetes Cluster
* Docker images registry - for storing your docker images, this could also be done within your CI server
* CSCloud - this will host your Kubernetes cluster and images registry. You will use it for CI server, testing ect.

### Evaluate an other groups development workflow
At the end of the course your group shall evaluate an other groups development workflow.
This means that you must provide adequate documentation on how to do that in your solution. This could be in the form of a README or a video tutorial. With this documentation one should be able to make a code change and make that go thru your pipeline into the production environment.

## Iterative meetings - Supervisor meetings
During the project the group will have meetings with the course management. There are several pass booked into the course schedule. This meetings are mandatory. Your group decides which of you that will participate in the meetings (all or just one person) but some should always be there.

During this meetings you should describe what you have done, how you have separated the work and how you will work until the next meeting. Try to keep these meetings effective and be prepared. These meetings are not meant for tutoring, if you're having problems with your solution you should book an tutoring session with the course management.

Some meeting have pre-defined topics that should be prepared in advanced:

* Meeting 1 - The group should have decided on a open source application and discussed the deployment pipeline
* Meeting 2 - The application should be up and running the production environment, this could be done manually
* Meeting 3 - ...
* Meeting 4 - ...

## Examination
The examination is divided i the following parts::

* Oral individual examination
  * Here you have to book a examination time with the course management and you will answer a few theoretical questions from the course.
* Group project
  * The artifact of the group work, should be provided in the Github group repository along with a group report. The report should describe the underlying system for the service delivery platform
* Individual report from the group work
  * In this project you should write a own individual group report to show your own involvement in the project (see below for more instructions)
* Group reflection on the other group development workflow
  * In the end of the course you should reflect on one other group's development work flow. Only one report per group.

The individual report should be emailed to 2DV611@lnu.se in PDF-format all other documentation should reside in the Github repository.

### Individual report from the group work

Since the grade is individual you have the chance to reflect over your (and the groups) work in a personal report. It will only be read by the examiners. The goal of the report is to show your involvement and understanding of the project along with a more detailed view of what you have done and how much time you have spend on the assignment. The following part should (at least) be part of the report. Feel free to add own headlines.

* Your work
  * What have you done in the project
  * Your time report
* Personal reflection of the project
  * Problems and solutions
  * What is good, what is bad
  * How have the group worked together
  * What have you learn during this assignment
  * What would you done in another way if you had the chance

#### Grading matrix
The final grade (A-F) is a grade based on all the above examination assignments.

A - For an excellent performance - the students have a very good knowledge of the subject and can discuss about the oral questions on a high level. The student have solved the assignments before the deadline and presented artifacts showing he/she have a high level of understanding for all aspects of the relevant material.

C – For a good performance - the students have a good knowledge of the subject and can discuss about the oral questions in a good way. The student have solved the assignments before the deadline and presented artifacts showing he/she have a good level of understanding for all aspects of the relevant material.

E – For a performance meeting only the minimum requirements for acceptance on each examination steps.

Fx – For a performance which does not meet minimum requirements for acceptance on each examination steps.

F – For a performance which is unacceptable in all respects.
