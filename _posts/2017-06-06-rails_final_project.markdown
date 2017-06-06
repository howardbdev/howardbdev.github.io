---
layout: post
title:  "Rails final project"
date:   2017-06-06 18:52:28 +0000
---

I decided to build an app that I could have used at my old job.  I worked as a departmental manager at a ski area, which means that I always had a million things to do.  At a mountain, like many other work areas, there is always a long list of things that need to get done, should have gotten done, and never got done.  Sometimes it gets challenging to keep track of all the things I need to have people working on, and I would make project lists and to-do lists that changed all the time -- definitely wasted some paper!

Hence, my app.  It's a very simple project manager that allows users to sign up, sign in, and log out.  There are four types of users, using an enum called "role": "worker", "supervisor", "admin", and "big_boss".  Basically, anyone can create a project.  Whoever creates a project becomes that project's owner.  Assignments link projects to workers, and can be made by any user whose role is greater than the project's owner's role.  Any worker who is assigned to a project can add a note to that project.  Users with greater roles than a project's owner can add also add notes.

Projects come with am enum called "status", which is "complete" or "incomplete".  They are very simple and designed with the outdoor aspect of a ski area in mind - which means projects are fairly simple and generall involve things like digging, fixing fencing or signs, and the like.

That's pretty much it.  Authentication happens with email & password or signing in with Facebook.  Authorization happens with a series of model instance methods and view helpers.

At the time of writing this post, I am not quite finished building and refactoring.  Already, this project has taught or reminded me of several valuable points:

- Refactoring is crucial!
- Building from scratch is *way* more challenging than getting a pre-built lab to work with!
- I don't know diddly!

Looking forward to continuing to learn how to put all this together!!!
