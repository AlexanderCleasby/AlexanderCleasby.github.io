---
layout: post
title:      "Web apps and DataBases? "
date:       2019-01-27 17:22:41 +0000
permalink:  web_apps_and_databases
---


SQL stands for structured query language, it has been around in some adaptation or another since the 70’s and there are a few different flavors companies use today from Oracle, Microsoft or others.  SQL servers are a separate process that only runs to store and retrieve data.  Other processes or servers can send data to be stored to the server or query data to be retrieved.  In the context of a web application databases are typically accessed via an API that uses query parameters in the url to construct a SQL query.  For instance I have [MERN stack app](https://your-timelog.herokuapp.com/) [(code here)](https://github.com/AlexanderCleasby/timelogs)that I have been building aside from my Flatiron curriculum that tracks how users spend their time.  One of the API routes I built takes a request with query variables year, month, day (and optionally lookback).  Here is an example of one of the API calls I pulled out of Chrome dev tools:
```
https://your-timelog.herokuapp.com/trackerapi/getactivities?year=2019&month=0&day=27&lookback=7
```
This API call is constructed by the React app, sends a request to the route trackerapi/getactivities with query variables asking for events of the past 7 days from today(in this instance January 26, 2019).  This call is picked up on the server and used to build and fire off a database query (in this instance Mongo DB not SQL, but the idea is similar)
```
   Activity.find({
           user: req.user._id,
           beg: {
               $gte: QueryDate.start,
               $lt: QueryDate.end
           }
       },
       (err, activities) => {
           console.log(activities)
           res.send(activities)
       }
   )
```
This then send back an array of activities to the client so react can present them in the UI to the user.

