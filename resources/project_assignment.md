## Project Assignment - 2DV611
This text will describe the project assignment for the course 2dv611 at Linnaeus University, Kalmar, Sweden. At first we will describe the problem to be solved. Later on in this text there will be a description of the seminar and then how the project it self should be performed.

### A deployment pipeline for Slack plugin developers
As then title above suggest will this assignment be about building a deployment pipeline for developer teams to develop Slack Plugins at the LNU CoursePress organization. [Slack](https://slack.com) is the communication tool teachers and students are using in LNUs Computer Science courses. [Slack have a platform for developing plugins](https://api.slack.com/) that could be used in the tool. The teachers realize that building their own plugins can simplify the workflow both for the teachers and the students. This is where you will fill the gap while making and configuring a development pipeline for developing plugins, update, version control, test, deploy and integrate them with external services.

The goal is to achieve a pipeline where teachers, students and external persons can develop their plugins in a transparent, easy and quality way.

This assignment will have several parts and learning objectives:

* Getting the understanding for making deployment pipelines, including adding CI-servers, testing and so on.
  * It will first be done as an individual theoretical preparation for a seminar, then implemented as a group assignment
* Getting a understanding for how to implement testing of software and application in the development pipeline
  * After the seminar you will be grouped together and your group will set up the deployment pipeline from the outcomes from the seminar
* Working in group with a real software project (see below) using integration techniques (VCS) using (your) deployment pipeline
  * Yes, there will be some coding and development, One group, many small commits, code always ready for production 
* Automate deployment in different environment maximizing the feedback speed of errors/bugs and the confidence in the code
  * Proper integration tests, notifications when failing and so on

We will not specify a long list of functional requirement. At this level you should be able to think about the problem and identify wanted features by your self. By reading the literature and article you will get the understanding of the parts implemented in a good deployment pipeline and how to bring your software and code changes to production in a fast, confident and secure way. 

#### How to prove you understand continuous delivery
As a group you must prove your deployment pipeline by working on a software running in the pipeline. Hopefully your pipeline will work for a broad spectra of software projects but in this course we will be focus on the Slack plug-in deployment when testing the pipeline. Of course you could do a "Hello World-example" but that won´t test your solution in a good way and you won´t learn how to work as a developer in this kind of environments. We are aiming for continuous Improvement!

To get a better understanding a more complex software project will need to be in place. **Every member of the team should do a lot of commits** and you should use the idea behind continuous integration to get the experience needed.

##### A time slot booking plugin - An example of a plugin to develop
At the moment the teachers have a suggestion on a plugin to use as an proof of concept when testing your pipeline. The below text is a description of what the plugin(s) will do.
In most of our courses we have some assignment with a oral examination. This examination is booked by the students directly in the learning platform. As things are today we are having trouble with a couple of things:

* Students can book a time before they have done a proper release and all tests are green
* If we close the time-booking the students can't see what time they have booked. That means that the time booking is available after the deadline meaning that students can book times until the last minute.

This means that the plugin(s) we are looking for should be able to do something like this - This could of course be discussed. this is not a requirement list but gives a hint of the size of the plug-in.

* When students do a release on GitHub for the course a web hook contacts a CI server (yeah, it will also be as a pipeline!) that pulls down the students source code and runs it against our tests. If failing the students should get an notification (issue) describing the problem, if success the student should be notified that they could now book a time slot through Slack.
* To book a time the student should write a command in the Slack chat for the course channel like `/bookexamtime`. The plugin should then check if the release is ok, if not the student should get a message that she/he can´t book a time otherwise the plugin will book a time (or a teacher) and notify the student about it.
* The student that have booked a time could ask Slack about it through a command like `/myexamtime`

Some more questions to think about

* How should the student be able to redraw her/his booking?
* How will all the booked times be visible for the teachers? A slack-command for teacher or a better visual solution.
* Should the student be able to rebook the time?
* If automating the whole thing - How could the teacher specify available time slots? Google calendar? JSON-file?

## Examination
The grade on this part is individual. The grading is from A to F, where F means fail. Here follow a short definition of some of the grades:

There are different examinations in this part

* Oral individual examination
  * Here you have to book a examination time with the course management and you will answer a few theoretical questions from the course.
* Group project
  * The artifact of the group work
* Individual report from the group work
  * In this project you should write a own individual group report to show your own involvement in the project (see below for more instructions)
* Reflection on the other groups work
  * In the end of the course you should reflect on the other groups work when trying there project (see below for more instructions)


### Individual report from the group work
Since the grade is individual you have the chance to reflect over your (and the groups) work in a personal report. It will only be read by the examiners. The goal of the repost is to show your involvement and understanding of the project along with a more detailed view of what you have done and how much time you have spend on the assignment. The following part should (at least) be part of the report. Feel free to add own headlines. 

* Background of the project
* Choice of technology - with motivation
* Your work
  * What have you done in the project
  * Your time report
* Personal reflection of the project
  * Problems and solutions
  * What is good, what is bad
  * How have the group worked together
  * What have you learn during this assignment
  * What would you done in another way if you had the chance

* Format: pdf
* Email: 2dv611@lnu.se

### Reflection on the other groups pipeline
In this step you should do a group reflection on the other groups work. This means that you as a group should test it and see how easy it is to work with, how the documentation is set up and so on.
Only one report per group. 

* Format: pdf
* Email: 2dv611@lnu.se


#### Grading matrix
The final grade (A-F) is a grade based on all the above examination assignments.

A - For an excellent performance - the students have a very good knowledge of the subject and can discuss about the oral questions on a high level. The student have solved the assignments before the deadline and presented artifacts showing he/she have a high level of understanding for all aspects of the relevant material.

C – For a good performance - the students have a good knowledge of the subject and can discuss about the oral questions in a good way. The student have solved the assignments before the deadline and presented artifacts showing he/she have a good level of understanding for all aspects of the relevant material.

E – For a performance meeting only the minimum requirements for acceptance on each examination steps.

Fx – For a performance which does not meet minimum requirements for acceptance on each examination steps.

F – For a performance which is unacceptable in all respects.
