---
layout: post
title:  "RTFQ - good advice, revisited"
date:   2017-05-09 19:52:22 +0000
---


About the time I started taking standardized tests, my dad gave me a particularly good piece of advice -- one whose value I could appreciate even when I was young and stupid and already knew everything.  "RTFQ," he would tell me before a test, "Read The Full Question."  (He said "Full," although there was a hint that I could add my own adjective.)  The meaning is simple but valuable -- make sure you read a given question carefully, and in its entirety, so you know what it is asking.  Excellent advice for students of any age or discipline.  One of the math questions I got wrong on my ACT (a college placement exam) asked for the new checking account balance after John writes Sue a $15 check.  I got the answer wrong because I didn't RTFQ and gave the new balance for the wrong person.  And I majored in math.

What does this have to do with programming?  I think it translates rather nicely.  "RTFS" or "RTFT" could be the new version: "Read The Full Spec" or "Read The Full Test," although the meaning is really the same.  RTFQ.  I know many times I have been stumped as to why my code is not meeting a particular spec.  it usually goes something like this:

Dammit, my code is perfect, it's doing what the test is asking.  The code works in console.  Works in IRB.  Formatting and syntax are correct.  SO says so.  So do the guides, so does API Dock so does google, and the WHOLE INTERNET, so WHY ISN'T IT WORKING!!!???!!!???!!!???

Well, did I ever open the spec file?  (*no*)  But.., ok, fine, I'll open it.  OOOOOHHHHHH! ** THAT'S** what it's asking!!!!!  OOOOOOHHHH!! DUH!

"But that's not exactly what the one-sentece test description says," I think to myself.  Or, "the test says it's testing the home route, but it's actually running through the login view first.  Sneaky bastards."  But it doesn't matter, just RTFQ.  Find out what the test is doing, what it's creating or assigning, what's happening before the test itself.  Read each line carefully to see how much of your code library is being called.

Checking spec files regularly has other benefits, too.  You can have a look and see what kind of instantiating is going on behind the scenes, or you can see what kind of test code is being used.  Sometimes, the spec files give away answers like what you need to name a method or what kind of params are required.  If you're reading the spec files with every lab, then by the time you have to write your own spec tests, it's a piece of cake.  You've already read those tests a thousand times, and you know exactly what to `expect`!


