---
layout: post
title: "CSESoc Hackathon 2018"
date: 2018-09-22
categories: blog hackathon
image: "/assets/img/csesochackathon.png"
credit: CSESoc UNSW
---

# CSESoc Hackathon 2018: Student Struggles

## The Theme
The theme for this years hackathon was 'Student Struggles' - any solution that could help solve a problem a student might have. 

## Our Problem
In our 3 man team, we decided that the problem we would tackle is forming study groups. It can be difficult finding people who want to study the same subject at the same time as you. Furthermore, if you have nobody to study with, you cannot book certain rooms like the study rooms in the library, so it would be helpful to have a way to find studymates.

## Our Solution
Our solution to this problem is StudyFast, a web app that allows users to post study group sessions, and browse open study group sessions from other users. The repository is available at [github](https://github.com/bowdens/microsoft_III).

## How it works
We split the solution up into two parts, the front end and the back end.  
The back end is a restful API which is agnostic to the front end implementation, which helped us develop both the front end and backend in parallel. The backend has a series of endpoints (most of which are documented on the [github README](https://github.com/bowdens/microsoft_III/blob/master/README.md).  
It was originally our plan to have users create an account to register for events but that became too complex for the prototype in about 8 hours of work.

### Front End
The front end is implemented with a flask server and Jinja for rendering the templates - we toyed with the idea of implementing the front end in angular but none our group members had enough experience with it to do this. It's not exactly the most appealing interface, but it mostly works.

### Back End
The backend is implemented again with a flask server using flask\_restful which makes it easy to create the API endpoints based on the classes we created for users and groups. There are a number of endpoints for various tasks including

* GET /user/id - for getting the details of a particular user
* POST /user/id - for creating a new user
* GET /user/id/subjects - for viewing the subjects that a particular user has published that they are in/have completed
* POST /user/id/subjects - for adding a subject to the list of subjects a user has published that they are in/have completed
* GET /group/id - get the details of a particular group
* POST /group/id - allows a user to join that group
* GET /group - gets a list of all groups
* POST /group - creates a new group

## My responsibility for the project
I had a little experience creating APIs so it mostly fell to me to design the endpoints. I'd probably change a few of them around (like move creating a user to POST /user instead of POST /user/id). I was also responsbile for implementing most of the user and subject based stuff, as well as some of the group class, and finalising some of the front end.

## What I might have changed
It was a good learning experience to create the separate front end and back end using the API, however given the short time we had it may have been better to reduce the complexity for the prototype. We could have saved some time by not having to worry about converting objects to and from JSON before displaying them on the front end.  
Our solution was not particularly original either. We had a few more original ideas but settled on this one because it seemed doable in the time. Perhaps in future hackathons I'd be more willing to tackle the more original ideas even if they are more complex in the time.  
Other ideas we had included a webapp that scraped the lab availability and automatically selected a lab for you to go to, an enrolment auto checker and/or booker, a UML class diagram generator from source code, and a task distribution system from source code (reads the class & method declarations and allows the delegation of tasks to group members for assignments).

## What I learned
I found it helpful to implement a restful server because it's not something that I had done fully before - I had done a little but this was the first time I had properly sunk my teeth into it, and I think it's good experience; there's lots of restful APIs out there.  
This hackathon also highlighted to me my lack of frontend skills. There's lots of classes at university which focus on algorithms and data structures, but none as far as I can tell which focus on front end stuff, which frankly is just as important in any kind of web app. So I'm going to make it a priority for me to try to learn a front end framework like angular at least enough so I can make something with it.
