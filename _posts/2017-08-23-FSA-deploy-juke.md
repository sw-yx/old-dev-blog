---
layout: post
date: 2017-08-23
title: FSA Deploy Juke
categories: FSA react deploy
tags: determined
---

What's that? It's time for another Deployment tutorial! The last three ([trip planner](https://sw-yx.github.io/2017/FSA-deploy-Trip-planner/), [twitter.js](https://sw-yx.github.io/2017/FSA-deploy-twitter-js/) and [wikistack](https://sw-yx.github.io/2017/fsa-deploy-wikistack-to-heroku/)) went pretty well but here we have another challenge - seed media files on top of simply seeding a PostgreSQL database!


So the core instructions are sited at the [wikistack tutorial](https://sw-yx.github.io/2017/FSA-deploy-Trip-planner/). Here I will focus on the incremental difference.

1. to configure `process.env.DATABASE_URL`, go to `server/db/db.js` and add it in there alongside `require(path.join(__dirname, '../env')).DATABASE_URI`
2. old `pg` dependency is gone
3. remember to create a table in SQL. this time, call it `juke`
4. to seed the db, `heroku run node ./bin/seed`
