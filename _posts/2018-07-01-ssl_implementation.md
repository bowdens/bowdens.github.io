---
layout: post
title: "Implementing HTTPS"
date: 2018-07-01 02:55:00 +1000
categories: security
---

I just read Troy Hunt's [HTTPS Is Easy!](http://www.troyhunt.com/https-is-easy/) blog post. He has posted a series of four videos on [www.HTTPSIsEasy.com](http://www.httpsiseasy.com) which quickly go through how to set up SSL on your website. And frankly, before watching these videos, my understanding of SLL and HTTPS was that it was some arcane magic with cryptography and certificates and certificate authorities that I'd never really bothered to understand. To be fair, after watching the videos I don't really know all that much more about how HTTPS works (other than that it encrypts stuff), but I do know how to implement it, which is great.

His implementation guide uses Cloudflare's free ssl solution, which is super easy, and is (according to his videos) more secure than some banks.

I've followed Troy's blog posts for a while and he is quite often talking about how more people need to implement HTTPS on their websites and this resource is really great for that purpose I think. 

Without HTTPS pretty much all of the data that is sent back and forth between the server and the client is totally unencrypted, meaning that an attacker could either read whatever you are sending or receiving (such as passwords or credit card numbers), or they could alter what you see - such as changing a bitcoin address to theirs so you send your bitcoins to the wrong place.

I used the guide to implement HTTPS on this site. To be perfectly honest, there's not all that much of a risk with this particular site. It's entirely static (it's using [github pages](www.github.com/bowdens/bowdens.github.io) and jekyll), and because github controls the servers and the certificates on the servers I can't properly encrypt the content that goes from the cloudflare servers to github. However using the guide I can encrypt everything that goes from [bowdens.me](bowdens.me) to cloudflare to be encrypted, which gives that nice green padlock you should be seeing in the top left corner.
