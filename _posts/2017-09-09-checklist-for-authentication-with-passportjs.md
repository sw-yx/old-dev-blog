---
layout: post
title: checklist for authentication with passport.js
categories: passportjs
tags: curious
date: 2017-09-09
---

Webapp authentication is important but complicated. This makes the process of documenting and teaching libraries like passport.js a difficult proposition. 

if your goal is to sell someone on how easily you can do something, your documentation is going to be scant on details (particularly if context is needed). this is the problem with [the official passport.js docs](http://passportjs.org/docs).

if your goal is to comprehensively handhold somebody through the process of adding authentication on an existing webapp, your tutorial is going to have a load of extraneous detail about the structure (in particular, assumptions about the frontend and the database stack) and it is going to feel like it never ends. In case it helps, here are the top google results for passport.js tutorial:

- [Starting with Authentication](https://medium.com/of-all-things-tech-progress/starting-with-authentication-a-tutorial-with-node-js-and-mongodb-25d524ca0359)
- [Node.js Authentication using Passport.js](https://blog.risingstack.com/node-hero-node-js-authentication-passport-js/)
- [Authenticating Node.js Applications With Passport](https://code.tutsplus.com/tutorials/authenticating-nodejs-applications-with-passport--cms-21619)
- [Authentication Using PassportJS](https://danialk.github.io/blog/2013/02/23/authentication-using-passportjs/)
- [Easy Node Authentication: Setup and Local](https://scotch.io/tutorials/easy-node-authentication-setup-and-local)
- [Tutorial for Passport.js authentication in a Node.js Express application](https://www.jokecamp.com/tutorial-passportjs-authentication-in-nodejs/)
- [Node.js, Express.js, Mongoose.js and Passport.js Authentication](https://www.djamware.com/post/58bd823080aca7585c808ebf/nodejs-expressjs-mongoosejs-and-passportjs-authentication)
- [Passport org on Github has maintained minimalist examples](https://github.com/passport)

I'm going to try to write for the person who is roughly familiar with passport.js/authentication that just wants a todo-list to check off as he/she implements.

---

# 1. NPM installs

Basic: `npm install passport express-session --save`

Strategies:

- Local: `npm install passport-local --save`
- DB specific: `passport-local-mongoose`
- Provider Strategies: `npm install passport-github` (or twitter or facebook and so on)

# 2. Require Express-session and Passport on Server 



# 3. Add routes

1. Provider Authentication
1. Provider Callback (e.g. `http://localhost:30000/auth/github/callback`)
2. Logout
