## Project Assignment - 2DV611
This text will describe the project assignment for the course 2dv611 at Linnaeus University, Kalmar, Sweden. At first we will describe the problem to be solved. Later on in this text there will be a description of the seminar and then how the project it self should be performed.

### A deployment pipeline for Slack plugin developers
As then title above suggest will this assignment be about building a deployment pipeline for developer teams to develop Slack Plugins at the LNU CoursePress organization. [Slack](https://slack.com) is the communication tool teachers and studnets are using in LNUs Computer Science courses. [Slack have a platform for developing plugins](https://api.slack.com/) that could be used in the tool. The teachers realize that building their own plugins can simplify the workflow both for the teachers and the students. This is where you will fill the gap of a working development pipeline for making plugins, update, version control, test, deploy and integrate them with external services.

The goal is to achieve a pipeline where teachers, students and external persons can develop their plugins in a transparent, easy and quality way.

#### A example of a wanted plugin
At the moment the teachers have a suggestion on a plugin to use as an proof of concept when testing your pipeline. The below text is a description of what the plugin(s) will do.

##### A time slot booking plugin
In most of our courses we have some assignment with a oral examination. This examination is booked by the students directly in the learning platform. As things are today we are having trouble with a couple of things:

* Students can book a time before they have done a proper release and all tests are green
* If we close the time-booking the students can't see what they have booked. That means that the time booking is available after the deadline meaning that students can book times until the last minute.

This means that the plugin(s) we are looking for should be able to do something like this - This could of course be discussed.

* When students do a release on GitHub for the course a web hook contacts a CI server that pulls down the source and runs the tests. If failing the students should get an issue describing the problem, if success the student should be notified that they could now book a time slot.
* To book a time the student should write a command in the Slack chat for the course channel like `/bookexamtime`. The plugin should then check if the release is ok, if not the student should get a message that she/he can´t book a time otherwise the plugin will book a time and notify the student about it.
* The student that have booked a time could ask Slack about it through a command like `/myexamtime`

Some more questions to think about

* Should the student be able to rebook the time? Get a couple of options?
* How should the student be able to redraw her/his booking?
* How could the teacher specify the time slots? Google calendar? JSON-file?
* How will all the booked times be visible for the teachers?




