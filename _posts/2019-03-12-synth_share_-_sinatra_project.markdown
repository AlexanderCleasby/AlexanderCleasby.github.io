---
layout: post
title:      "Synth Share - Sinatra Project"
date:       2019-03-13 01:11:59 +0000
permalink:  synth_share_-_sinatra_project
---


For the second project in the Flatiron School curriculum we were tasked with creating an App using the Sinatra framework and Active Record to demonstrate our understanding of those frameworks and more over the HTTP request/response cycle.  The concept I came up with for the project was a program for building simple synths using synths using the excellent Tone.js and storing those synths in a database where they can be retrieved later and shared with other users. Sinatra is web framework for Ruby that allows the user to set routes and send responses.  Active Record is a ORM for SQL databases that we will be using to handle all our database operations.  

Our database structure for this project will be thus: a table of users that contains the username and password field.  A Synth table that contains a foreign key to join to the users table and a name for the synth.  Then an Oscillator table that has a foreign key to join to the Synth table and attributes for each of the attributes for the oscillator, for now we have ASDR and detune.

![](https://i.imgur.com/5qxNwjH.png)
  
The root route “/” displays a flex-box ul containing all the synths in the in the databases and a link to view and play the synth.  Each view route, “/synths/:id”, renders from an erb template a playable keyboard (from the tone.js-ui library) and a series of ranges and dropdowns to control the type of oscillator for each of the three oscillators and some attributes the user can manipulate.  Also the template checks the synth being viewed User_id against the user id stores in the sesion.  If the synth belongs to the user they will be able to update it.  If the user is authenticated then they have the option to save their own copy of the synth with adjusted params.
The “/synths/new” route returns a view similar to the “synth/:id” route, but the synth’s default parameters will be selected so the user has a clean slate.

