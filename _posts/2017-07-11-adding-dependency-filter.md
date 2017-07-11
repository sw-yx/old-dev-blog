---
layout: post
title: adding dependency filter
date: 2017-07-11
categories: projects
tags: determined
---

next feature. the dependency filter should be relatively easy to do but i will need to redo the inputs since I dont store them separately. tasks:

- remodel the input to save dependencies and devdependencies (let them join its ok).
- create an api to retrieve the dependencies (no need for count) `documents.dependencies`
- create the filtering api and modify in `documents.list`
- create the frontend to use the two api's - basically an autocomplete search bar to know what to include
