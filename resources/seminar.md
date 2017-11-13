## The seminar
This text describes the seminar taking place in the course 1dv611. This seminar will be about the described [project assignment](https://coursepress.lnu.se/kurs/continuous-delivery/examination/project-assignment/).
This seminar is an individual assignment meaning that the preparation will be done by the single student and the result will be presented and discussed in groups.

The seminar group will be the same group you will work with later on in the course so we can see this as an seminar/workshop before we will start the group assignment.

### Groups <br />
**Group 1**
Johan Gudmundsson <br />
Francis Pi <br />
Martin Sigfast <br />
Fredrik Olsson <br />
Fredrik Wällstedt <br />
Leif Karlsson <br />

**Group 2** <br />
Axel Nilsson <br />
Andras Balla <br />
Pär Eriksson <br />
Olga Christensen <br />
Tommy Kronstål

## To do
In this seminar the idea is that everyone should be well informed and prepared with the problem and have done some thinking about possible solutions. Hopefully during the seminar the group could give each other good feedback and the group as one can find a good solution together.

The following should be done and considered before the seminar:

* Draw a picture over how the deployment pipeline could look like for the project assignment (the slack plugin development pipeline)
  * Be prepared to motivate your decisions
* How does your model avoid the anti-patterns described in chapter one in the course literature?
* You probably need some CI server; investigate different kinds and try to compare them. Motivate a choice.
* How will your pipeline build confidence into the code?
  * How and where will the code be tested.
  * Where will unit tests runs, integration tests...other tests? Non-functional?
* Which steps will be fully automated, which will be manual?
  * Motivate your choice!
* Which environments will your pipeline have? How do they differ?
* How will the deployment to production happen? Techniques? Containers? Why?
* How will we learn others developers to use the pipeline?
* Which tools do we need when building our pipeline?
* Should we always work against "Coursepress Slack" when testing?
  * Create a own Slack organization while testing?
  * Using [GitLab](https://gitlab.com) or create a own GitHub organization?
* How will the infrastructure look like in the different environments?

