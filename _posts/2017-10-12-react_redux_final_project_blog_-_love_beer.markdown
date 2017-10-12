---
layout: post
title:      "React Redux Final Project Blog - Love Beer"
date:       2017-10-12 11:42:49 -0400
permalink:  react_redux_final_project_blog_-_love_beer
---


I built a simple React/Redux app that allows beer lovers to share beers they like.  Users can create a new beer, view beers, and upvote or downvote beers they like or dislike.  RESTful routing is incorporated using `react-router` and `react-router-dom`.  I did have some trouble with matching too many routes, for example, requesting `/beers/new` would match both `/beers/new` (correct) `/beers/:id` (not what I wanted).  At first, I just changed the url for the show page to `/beer/:id`, which solved the problem, but of course also deviated from RESTful routing practices.  This bothered me, kind of like a small stone in my shoe, until I *had* to fix it.  Of course there is always a way!  The `Switch` wrapper from `react-router-dom` was the solution.  By wrapping the `<Routes/>` in `<Switch>` tags, like so,

```
<Switch>
  <Route exact path="/" render={Home} />
  <Route exact path="/about" render={About} />
  <Route exact path="/login" render={Login} />
  <Route exact path="/beers/new" component={BeerForm}/>
  <Route exact path="/beers" component={Beers}/>
  <Route path="/beers/:id" component={Beer} />
</Switch>
```

, only one route matches any given request, which solved my problem!

Then, from a beer show page, accessing the `:id` property is a breeze with `props.match.params.id`!  One of the more cumbersome pieces of my code is deciding whether to redirect after submitting to create a new beer object.  Since creation is handled on the back-end, there's no (easy) way (that I've yet found -- there probably is!) for the `handleSubmit` function to know whether a beer was successfully created.  My solution is definitely feels like a hack!  Here is it: 

1. I imported `{ withRouter }` from `react-router` in my form container.
2. I declared a const `length` at the first line of the `handleSubmit` method and's set it equal to the length of `beers` in the current state.
3. I added an `if` statement inside a one-second `setTimeout` to check if the state (`state.beers`, in my case) had grown since the `handleSubmit` started.
4. If so, I used `this.props.history`, which comes from importing `withRouter`, to `.push` the newly created beer's show url to the `history`.
5. This also felt a bit hacky, since you can't use `[-1]` to access the last element of a state array (I haven't figured out why), so I had to use `this.props.beers.length - 1` as my index, and call `.id`.  The full line of code looks like this:

        this.props.history.push('/beers/' + `${this.props.beers[this.props.beers.length-1].id}`)

Ugly, for sure.  And, of course, it won't work if the request takes more than one second to come back.  NBD, though, as the user would just be looking at a form and the beer would be there upon navigating to the beers index.  If anyone comes up with something more elegant, I'd love to know about it! (I did find some elegant solutions, but they were for static urls and instances where there was no need to wait for a good response from a back-end API.) 

I am excited to continue to learn React/Redux, and see how it evolves.  Snappy, single-page apps are becoming more common, and now I can build them!!!

Thanks for reading.
