---
layout: post
title: "Holder: A digital, live bag of holding"
date: 2021-02-18
categories: ['blog','project','holder', 'web dev']

image: "/assets/img/holder.png"
---

[Holder](https://polybius.bowdens.me) is a website I created to allow D&D (and other tabletop RPG players) to move away from keeping track of all of their items in a bag of holding with pen and paper, and instead use a website where bags can be shared between party members and any changes to the bag are updated in real time between all users.

## Hold on: Bag of holding?
So if you're not familiar, D&D is a fantasy tabletop roleplaying game, and one item that is quite commonly used in it is a bag of holding - essentially a magic bag that lets you put way more things inside than a regular bag would.

## So why do we need a website?
Well I ran into this problem when I was DMing (essentially running, for the unfamilari) a game for my party and in one session, the person who was supposed to be tracking the items in the bag of holding didn't show up and so we had no idea what was inside. Then the next session it turned out they hadn't been tracking it at all and thought someone else was tracking it - you can see the problem. So I began working on a web app to solve this issue.

## Alright, what can it do?
Well if you go to the link above you can check it out. You can make a new bag (which will generate a code to share), or enter someone else's code to join their bag. No sign up required. Then when you're connected you can add D&D items to the bag (thanks to the D&D items released under the Open Gaming Liscense by Wizards of the Coast), or add your own custom items. If multiple people are connected to the same bag it will automatically update the items in both devices.

## Sounds good, what tech did you use?
I made the full stack myself and the technologies are as follows:
### Frontend
The front end is built using react. It uses react-redux for managing the state, and react-bootstrap for the nice components.
### Backend
The backend was built using express although the vast majority is not really express; it's socket.io. That's how the live updaing functionality works, with websockets. Socket.io has some really nice functionality called rooms, where clients can connect to a room (in this case a bag), and the server can emit events to all clients connected to the room.

The database is mongodb. Since mongodb is nosql, it made it much easier to store all of the items in a bag in embedded documents rather than in separate tables like a traditional sql database.
