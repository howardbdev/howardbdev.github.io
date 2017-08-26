---
layout: post
title:  "Rails JS Final Project"
date:   2017-08-26 20:40:24 +0000
---


Well, this is awesome.  From CLI, to Sinatra, to Rails, and now finally JS - seems like I've come a long way.. and I know there's plenty more to go (always)!

Ths app is an extension of my final Rails project - a project management app designed with an outdoor company in mind.  It suits me because it's where I came from in my old job - and I could have used something like this to keep my projects organized.  This app still utiilizes BCrypt and OAuth for security and external login (via Facebook).  Users can log in and out, create and edit projects their own projects, and add notes to projects they've been assigned to.  There is a four-tiered enum called role, and bottom-to-top is `worker`, `supervisor`, `admin`, and `big_boss`.  Users can make project assignments and edits to those they outrank.

The new features are a JSON API on the backend and jQuery implementation to allow viewing and creating objects without a page refresh!  This is really awesome stuff to learn and put in motion.  As of the time of writing this post, the API backend, along with `$.get` methods, allow users to view a users index, projects index, and projects show page - all on their home profile page.  Also, project notes are now created and deleted via `$.post` and `$.ajax` methods!  No more page refreshing there!

The API is currently open to any logged-in user.  The easiest way to access it would be to add a `.json` extension to any user, project, or tool route - show or index.  For example, the JSON projects index is found at `/projects.json`.  To view API endpoint for user with an id of four, head to `/users/4.json`.

I feel as though this project is a warp-drive leap ahead in app implementation, and yet I know I'm still at the very beginning... this is really exciting!

I have watched approximately 419 hours of tutorial videos now, from Learn.co and otherwise, and I'm finding that to be a tremendous help with all these new topics.  Also, YouTube's video speed adjustment feature is a god-send - some teachers just talk slowly.

I look forward to continuing to refactor and move of to what's next!

Thanks for reading.
