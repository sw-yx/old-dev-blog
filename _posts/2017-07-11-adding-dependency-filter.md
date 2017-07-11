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

---

remodel went well.

i was wrong to want to create a separate api to retrieve just the dependencies. [you cannot call the search on the same collection multiple times](https://docs.meteor.com/api/collections.html) which is mildly annoying (here is a SO question on [this big topic](https://stackoverflow.com/questions/19826804/understanding-meteor-publish-subscribe/21853298#21853298))

I am going to just do the next two points on the clientside.

---

2.5 hours later and this is done!

[boilerplate dependency search](https://twitter.com/swyx/status/884675880236306436)


I have also open sourced it <https://github.com/sw-yx/packageJason>
