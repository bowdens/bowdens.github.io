---
layout: default
title: Libtalaris
---

# Libtalaris

Libtalaris is a C library for creating interactive command line interfaces easily. It focusses around commands and callbacks, with each command executing the callback and passing the arguments into it in the same was as arguments are passed in `main(int argc, char **argv)`.

I originally started developing libtalaris not long after learning C, because I couldn't find a simple to use library that did what I wanted. It's been about a year since I started working on it, on and off, and its gone through a lot of changes (you can see the original version at it's [github page](https://www.github.com/bowdens/input-handler) - before I had even named it).

The new version makes use of [uthash.h](http://troydhanson.github.io/uthash/) and [utlist.h](http://troydhanson.github.io/utlist.html) to store & retrieve the commands, and to split up the string entered by the user into seperate strings (although that particular part - wordsplit.h, needs some work put into it, it's not great at the moment).

See more about libtalaris and download it at it's [github page](https://www.github.com/bowdens/libtalaris).

Libtalaris is licensed under the MIT license.
