## Project Assignment - 2DV611

This text will describe the project assignment for the course 2DV611 at Linnaeus University, Kalmar, Sweden.

### A deployment pipeline

The assignment is a group project where you should develop a deployment pipeline supporting a continuous delivery workflow of an open source web application. Which web application you will use is up to the group to decide based upon the work you did in the reports.

The deployment pipeline should be build for a developer team to continuously develop and maintain a web application. The goal is to achieve a process where a new developer can continue the development of the application in a transparent, easy and quality way.

This assignment have several parts and learning objectives:

* Getting the understanding for producing deployment pipelines, including CI-servers, artifact repositories and so on.
* Getting a understanding for how to implement automated testing of software and application in the deployment pipeline
* Working in group with a real software project with some bigger code base and test suits. 
* Automate deployment in different environment maximizing the feedback speed of errors/bugs and the confidence in the code
* Getting the code changes all the way to production
  * Your web application should be running in a production environment as a last step of the deployment pipeline.

<br>
We will not specify a long list of functional requirement. At this level you should be able to think about the problem and identify wanted features by your self. By reading the literature and article you will get the understanding of the parts implemented in a good deployment pipeline and how to bring your software and code changes to production in a fast, confident and secure way.
We are aiming for Continuous Improvement!

### As a individual project member
To get a better understanding of a more complex software, all project members must be active throughout the development. **Every member of the team should do a lot of commits** and you should use the idea behind continuous integration to get the experience needed. You should use some kind of ticket/issue system that will allow you to plan your work and for the examiner to view the individual work in the group. 


### Tools at your disposal
To facilitate you in this assignment, we will provide you with a variety of tools and systems if you want. You are free to choose your own (otehr public cloud, SaaS:s and so on). The following will be provided for you never less.

* 2DV611 organization Github repository - should be used for the examination artifacts and maybe planing
* Kubernetes Cluster - Two clusters per group
* CSCloud - this will host your Kubernetes clusters where you should be able to install different kinds of servers/software you need.


## Iterative meetings - Supervisor meetings
During the project the group will have meetings with the course management. There are several pass booked into the course schedule. This meetings are mandatory. Your group decides which of you that will participate in the meetings (all or just one person) but some should always be someone there.

During this meetings you should describe what you have done during the week, how you have separated the work and how you will work until the next meeting. Try to keep these meetings effective and be prepared to guide the examiner through your progress. These meetings are not meant for tutoring though.

Some meeting have pre-defined topics that should be prepared in advanced:

* Meeting 1 / course week 5 - The group should have decided on a open source application and discussed the deployment pipeline
* Meeting 2 / course week 6 - The application should be up and running the production environment, this could be done manually
* Meeting 3 / course week 7 - ...
* Meeting 4 / course week 10 - ...
* Meeting 5 / course week 11 - This meeting is optional.

See below for more info about the meetings

## Examination
The examination is divided into the following parts::

* Oral individual examination
  * Here you have to book a examination time with the course management and you will answer a few theoretical questions from the course.
* Group project
  * The artifact of the group work, should be provided in the Github group repository along with documentation. 
* A documentation for a new developer
  * The group should provide a documentation for a new developer that will start working on the software.
    * Be sure to describe the underling process for each step, where the developer can find information. What will happened when errors occur, where to visually view the result and so on.
  * The examiner will follow these instructions to evaluate the pipeline so put some effort in the documentation!


The individual report should be emailed to 2DV611@lnu.se in PDF-format all other documentation should reside in the Github repository.

### Individual report from the group work

Since the grade is individual you have the chance to reflect over your (and the groups) work in a personal report. It will only be read by the examiners. The goal of the report is to show your involvement and understanding of the project along with a more detailed view of what you have done and how much time you have spend on the assignment. The following part should (at least) be part of the report. Feel free to add own headlines.

* Your work
  * What have been your focus in the project
* Personal reflection of the project
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
