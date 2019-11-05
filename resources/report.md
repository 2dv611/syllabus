## Kicking off the project
This text describes the report in the course 2DV611. This report should be an individual written report.

### About the report
In this report you should show that you have a good understanding of the theoretical parts from the first lectures in the course but also done some investigation and thinking before the project assignment starts. The report shall be divided into five different part.

The report must use the [IEEE reference system](https://ieee-dataport.org/sites/default/files/analysis/27/IEEE%20Citation%20Guidelines.pdf)

### Part 1 - Introducing the problem context
In the first part you must explain the context for the reader. Try to describe the idea behind "Continuous delivery". What is the problems it wants to solve and what benefits will it give to a software project? How will it affect the software development? Some words that may be sutible to add into your own written text could be:

* Continuous Integration
* Continuous Delivery
* Continuous Deployment
* Service deployment patterns
* Delivery pipeline


### Part 2 - Investigation of CI-servers
In this part of the report you should investigate and present your findings about at least three different CI-servers. One of them must be [GitLab](https://about.gitlab.com) though. Here are some point that at least should be appointed in the report:

* A summery of the core functionality of the product
* The ability to build pipelines
* Description of the license of the product
* Handling of artifacts (building and artifact repository)
* The support for notifications during the build process
* Support of containers and Kubernetes


### Part 3 - Finding an open-source web application project
In this part you shall describe your findings when trying to find an open source web application that could be used when building a delivery platform. You are pretty free to chose what ever project you like but you should be prepared to motivate your choice. There are some point to think about that you should point at in your defending of choice:

* The project should have a test suit since that is an important part of the delivery pipeline and you don´t what to write a whole test suit yourself (in this course)
* Think about the ability to change code. You should try your pipeline solution often and as real as possible so think about the complexity of the project, how easy it will be to make sensible and realistically code changes
* Think about the production part of the project. How easy will it be to put in production? Which components do it need except the application. Is it easy to containerize?
* Do you have some personal motivation for choosing this project? How is it suitable for the project assignment? Do you have a personal interest in this source code?
* Could you identify some risks with your chosen application?
* ...

### Part 4 - A draft of the pipeline
Try to make a first draft of the delivery pipeline that could be suitable for the project assignment. This will not be a final version and hopefully it will evolve during the group assignment but try to create a first version with, what you think is, suitable steps, gates and flows. Where will artifacts be created? Where will they be stored? Identify gates and steps. Notifications?
Remember that this is just a first draw and more of a discussion material for further discussion later on when the group assignment starts.

### Part 5 - Summarize your findings
In the end of the report you should summarize your findings and your own opinions. Try to motivate your choice of open-source application. Which CI would your prefer and why? Try to think of this part as a text your project members will read before you have your meeting where you decide of which path to take.

### Handing in the report
In the preliminary planing you will find the date for the first hand-in. It will be a peer-review and during the same day you should get an e-mail with further instructions.


### Examination of the report
The examiner will look at these parts:
 * The students knowledge in the area
 * The students ability to search and present information for the reader (including using references)
 * The reflections the student presents from the pre-work step to his/her final solution
 * The effort the student put in the work. **We won't specify number of pages (you should be able to estimate that for your own) but would not hesitate to fail reports done with low or none effort.**
