---
layout: post
title: "AB Testing in a Single Page App"
description: "Using Google content experiments with a backbone app"
category: development
tags: [backbone.js, ab testing]
---
{% include JB/setup %}

For the last year I've been working on building a new web application using backbone.js
to drive all our ui.  In a lot of blogs I've seen this referred to as a single page app (SPA).
For someone who has been doing web development for 15 years the transition to the SPA mindset
took a bit of adjustment, but overall I've been pleased with the result.  

One area that continues to cause us issues as we integrate in other services is the assumptions
that are made about basic things like page onload.  In a traditional web application assuming
each page will generate an onload is a pretty safe one.  However for an SPA, it's not and
getting around that assumption can be a challenge.

Our most recent run in with this was in integrating Google's new Content Experiments into our
site to do some AB testing.  In a "normal" implementation content experiments will rewrite
the URL to direct the user to the variant it wants.  For some cases this did not cause an 
issue in our app.  If the user refreshed however things got messy depending on where
they were in the application.

At first I didn't think there were any other options, but eventually found some interesting
posts at Conversion Works blog (http://www.conversionworks.co.uk/blog/2012/06/18/google-content-experiments-testing-templates-and-sitewide-content/)
Based on their experience we modified the GA CE JavaScript to set the combination variable
and changed our Backbone view to behave differently based on which one is set.  From our
initial testing seems to work well.  In a later post they note needing to add a query
parameter if you want visits to be shown correctly in the  content experiments UI.
