---
layout: post
title: "Badgery's Creek Locksmiths"
date: 2019-02-06
categories: ['blog', 'project', 'AWS', 'web dev']

image: "/assets/img/badgerys.png"
credit: Badgerys Creek Locksmiths
---

[www.badgeryscreeklocksmiths.com.au](http://www.badgeryscreeklocksmiths.com.au) is a website I've recently created for Lock Logic who are now operating under the additional trading name of Badgerys Creek Locksmiths.

## Motivation
I was asked by the owner of Lock Logic (who also happens to be my dad) to create his new website for Badgerys Creek Locksmiths as he aimed to expand his business' reach into that area. I also took this as a good opportunity to cement my understanding of basic HTML, expand my understanding of CSS, as well as delve more into basic javascript. 

For the back end I also saw an opportunity to become at least a little bit familiar with AWS, so the website is hosted on an EC2 instance running a flask server.

The website is supposed to attract customers in the Badgery's Creek and surrounding suburbs area. For that reason, there is a landing page for each surrounding suburb. (For example, [www.badgeryscreeklocksmiths.com.au/badgeryscreek](http://www.badgeryscreeklocksmiths.com.au/badgeryscreek))

## The Front End
I intentionally went into this project not using any web frameworks so I could get a good handle on the basics of front end web development.

My philosophy for this website was to make it as fast as possible to load - and having no frameworks helps in that regard. To also help with this, most of the website content is on a single page. When the user clicks a link in the navbar, it just scrolls down to the relevant part of the page instantly - no loading required.

(as a side note I think I seriously overengineered the navbar. It's all set up to use javascript to scroll to the relevant section of the page depending on the position of the section and the size of the navbar. It also changes the highlighted link depending on the position of the page - there was undoubtable an easier way of doing this than the way I did it, but it more or less works).

## The Back End
As mentioned at the start, I used this project as an opportunity to dive into AWS and cloud computing. The website is currently hosted on a free tier EC2 instance, which after some false starts with private key problems and issues with python (when can we all agree to stop using python2?) I managed to set up the instance and the flask server.

In truth I'm not really using flask to it's full potential here. The website is pretty much static - although I had toyed around with the idea of setting up an automated text messaging service using twilio on the webserver, but in the end that feature was rejected.

I use apache and WSGI to take incoming requests and send them to the flask server which is a fairly standard setup. However before this I had never used a flask server in production so there was a lot to figure out with regards to domain matching for the www and m domains.

## Reflection
There is still a few things that need to be fixed up on the website. The scaling isn't right on certain mobile browsers and the website starts zoomed in. I also need to figure out how to automatically redirect mobile traffic to the m subdomain - and to also make the m subdomain more mobile friendly; currently it's not much more than an increase to the font size and a different navbar.

I learned a great deal from this project. I feel very comfortable now with CSS and javascript which I was not entirely before - I still have more to learn of both languages but I think I could work on similar projects without too much crawling through stackoverflow and documentation for how to do certain things. The next step for me here is diving into various frameworks. I've already done a bit of jQuery and bootstrap and I want to look more into those, as well as something like Angular of Vue.

I also learned how much there is still to learn about cloud computing and AWS. I did manage to set up the EC2 instance as well as flask and apache, but AWS is an endless pit of things to learn. My next in that regard is databases - both on AWS and in general. SQL has come up in several courses at uni, but never in a substantial way and I've never had a good project to get properly stuck into it.
