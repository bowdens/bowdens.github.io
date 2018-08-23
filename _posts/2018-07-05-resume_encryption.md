---
layout: post
title: "Encrypting private data on a static website"
date: 2018-07-05
image: "https://upload.wikimedia.org/wikipedia/commons/c/c9/Locked_document.png"
credit: "Lydia Kim"
categories: blog
---


When I was creating this website I faced a problem. I wanted to have my resume available on here, but I really didn't want anybody to be able to just view it. Obviously the answer here is to have some kind of password that I could distribute to the people who I wanted to see the resume, and have the server validate the password(s).
However this is a static website (using jekyll), hosted with github pages, so it is not possible to have any kind of server side validation - I needed a new method.

What I came up with is to convert my resume into HTML, encrypt it, send the encrypted version to everyone who accessed the page, and then use Javascript so that the client can decrypt the resume if they have the right key.

I had to do a fair bit of research on how to do this - I'm pretty new to javascript and thus far have only really dabbled in it. So I looked around, and it seemed to me that the best encryption library was [CryptoJS](https://www.npmjs.com/package/crypto-js), which is a package from Google. It's pretty simple to use, you simply create a ciphertext object using `CryptoJS.AES.encrypt(plaintext, key)`. Similarly you can decrypt using `CryptoJS.AES.decyrpt(ciphertext, key)`.

So all in all, what I did was pretty simple. I took my HTML, encrypted it, served it up in the [cv page](/cv), and then had the user enter a key and try to decrypt it clientside, using the CryptoJS package.
