---
layout: post
title:      "Custom Dash Project Write Up."
date:       2019-09-19 01:10:33 +0000
permalink:  custom_dash_project_write_up
---


For my last project as part of the Flatiron course I chose to really push myself and come up with something creative and challenging.  The project was meant to demonstrate a competency with React and Redux and be the centerpiece of a student’s portfolio.  While I have a project that I have spent more time on that might surpass this project in polish I am maybe more proud of this project and the hurdles that I climbed to get this project presentable.

![very good|512x397,20%](https://i.imgur.com/4tiAviV.png)

The concept I had in mind was this: build a web  app where the user can compose a dashboard for public display that can contain a number of different “widgets” that can be added to in a modular fashion.  At this stage right before I schedule a project review I have only 2 types of widgets available, but I hope I have set this up in enough of a modular way that this can be easily added to.  

What is needed to create a new widget is 2 things, a stateful component to display the widget’s body in the dashboard editor UI, and a component functional or stateful to handle displaying the widget.  The UI component is where the user can add the UI inputs and bits of state that handle the user’s inputs that determine the widget’s configuration.  This component extends the widget component and must contain 2 essential methods.  
The renderBody method, which contains the UI elements that will render inside of the widget.
An ops method that returns the widget’s configuration that will be sent to the Rails API and saved to the database.

