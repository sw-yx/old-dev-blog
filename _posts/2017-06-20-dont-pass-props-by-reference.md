---
layout: post
date: 2017-06-20
categories: pup
title: Dont pass props by reference
tags: happy
---

I have been battling a particularly terrible bug with a nested react component for the past day and only just solved it. The problem essentially was that I had a component (A) that was nested in another component (B), and when I unmounted B (B1) and switched to another instance of B (B2) the values from A (that were valid in B1) were somehow persisting in B2.

The reason this was happening is that I was instantiating A by supplying props from B, and then within A I was modifying those props so it could be read back again by B. However this modified my defaultProps within B and _THOSE_ persisted when i switched from B1 to B2.

god damn.

---

3.00. my task now is to add deleting capability to the guestEditor.

---

3.15. my task now is to port the guests module to the segments module.

the subtask is to create a timepicker. the ones i have tried arent good so I will have to do it myself.
