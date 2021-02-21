---
layout: post
title: "Capstone Project: Ultracast"
date: 2021-02-21
categories: ['blog', 'project', 'web dev', 'ultracast']
image: "/assets/img/ultracast.png"
---

Ultracast (or BroJogan, a pun on Joe Rogan) is the name of the capstone project that I made with a team of four others in 2020. It is a podcast web app on which users can listen to podcasts, have their progress saved, subscribe to podcasts and be notified of new episodes, and have podcasts recommended to them. The source code is available [here](https://www.github.com/bowdens/ultracast).

Ultracast has three main sections: The frontend, made with react; the backend, made with flask-restful; and the database, a PostgreSQL database. Our team used the agile methodology for the project.

In our first sprint (after coming up with the user stories and assigning points to each), I was assigned the tasks of implementing the database and getting it loaded up with some test data so we could begin work on the front and backend. I used a digital ocean server I had for a reddit bot to host a postgres instance so all of our team could use the same database with the same data in each.

In the second sprint I created an rss scraper which could grab all of the relevant details from a big list of podcast rss links I had found on the web. It also fell to me to begin work on podcast playback on the front end (which was difficult because before that point I had not worked with react, or even that much javascript). Nevertheless, I figured it out and implemented a working playback system that also called the backend API every 30 seconds (or when paused) to save the user's progress in the podcast episode.

In the final sprint, I was tasked with creating a recommendation system that operated on the database level. We had originally implemented a recommendation algorithm on the backend but the problem was that it made far too many individiual queries to the database, with each having the overhead of accessing a remote database that was hosted in the United States. So instead we wanted the recommendations to be a plpgsql function that the backend could call in 1 request and get all of the recommended podcasts. It took some effort and a lot of help from my team mates, but eventually we got the recommendations algorithm working. 
I also got the job of implementing notifications so that when a new episode of a podcast came out, the subscribers to it would get a notification. This posed a problem because up until this point we had not been storing all of the episode data in the database; it was up to the client to fetch the rss feed and get each episode, and we'd only store the episode IDs in the database. However with notifications we'd need to regularly check each podcast in the database to see if there were new episodes, and this could be really taxing with a lot of podcasts in the database if implemented improperly. What I ended up doing for this, was to check for new episodes at most once every 10 minutes per podcast, and only when a user requested that particular podcast. So it could be when the podcast was searched, or viewed, or even when it was requested as part of a list of their subscriptions. That way if a user logged on and the client requested their subscriptions, the backend would spin up a thread that would first check if the podcast had been updated in the last 10 minutes, and if not fetch the RSS feed and make any updates if new episodes had arrived.
That also meant I had to go back and redo my rss scraping so that each podcast had each of its episodes already in the database so when the backend checked for updates it wouldn't load in all 1000 of a podcasts episodes at once and spam the user with notifications.

The project was a lot of fun, and all of our team members contributed well which is always nice in a uni project. I learned a lot, both about agile development and about technologies which were new to me, like react.
