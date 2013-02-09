---
layout:   post
title:    Ajax... JSON or Partial HTML?
---

Single Page web applications can be a good way to enhance a user's experience.
When developing single page web apps, what content type should you return in your
responses? Recently, I came across this advice:
["Never, and I mean NEVER return marked-up data using AJAX (use JSON)"](http://codereview.stackexchange.com/questions/19710/better-way-to-return-data-via-ajax/19723#19723)

For a long time, I have agreed with this assertion. It makes sense right? JSON 
is small, HTML is big. But, is that all there is to it? Will a user really notice
the difference?

I created a simple [demonstration](http://ajaxdemo.pagodabox.com/). Open it 
using firefox or chrome and view the net tab in either firebug or developer 
tools. You can view the difference by submitting the form with either json or
html selected. Sure enough, html is bigger (514b v 145b). And, json is faster
(1.47s vs 1.52s). 

But, can you really notice any difference? I can not. And unless your application 
is going to be serving tens of thousands of requests each day or your responses
are very large (which they generally aren't), your users won't notice either.

There is another consideration too. If you use json, you then have to write
more javascript to map the json data to your forms or other views. If you use
partial html, there is no mapping needed.
<script src="https://gist.github.com/robap/4747480.js">
</script>
<noscript><a href="https://gist.github.com/robap/4747480">View Gist</a></noscript>
