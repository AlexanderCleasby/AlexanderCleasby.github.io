---
layout: post
title:      "Implementing Rails in the "Taskaroo" app."
date:       2019-07-14 20:27:11 +0000
permalink:  implementing_rails_in_the_taskaroo_app
---


for the fourth project in the Flatiron program students were asking to implement come client-side JS where logical into the Ruby on Rails app  that  they made for the last project to do things like store info (using ES6 classes), fetching and posting information  from the back end using API routes, and updating the rendered veiw.  For my project, "Taskaroo" there were some pretty clear enhancements that could be made by moving away from rendered views to a responsive UI.

One such place is in the  **List Show** action, in the past this page would be rendered entirely by the server and the resultant view would be sent to the user as ready to go HTML.  This is bad because adding additional tasks (from the form that is rendered on the Show page) would necessitate that the form data be sent via a POST request, a redirect response get sent back to render the List Show page again.  Luckily thanks to Turbo Links being implemented in Rails this isn't as jarring as it could be, but this is still a really bad way to handle this use case.  The fix I implemented here was to set up an API that would return info about the list and it's tasks as JSON (/list/:id.json) and use the fetch to get that data create instances of the JS class Tasks and use a method on that class to render html to the view.  

```
    render() {
        // Create the elements that comprise the list variable
        let li = document.createElement('li')
        let title = document.createElement('div')
        let button = document.createElement('button')
        let icon = document.createElement('i')

        //Apply appropriate styles to the new elements
        //TODO: we can use scss to consolidate this.
        li.className = "list-group-item d-flex  align-items-start listDo"
        title.className = "ml-3"
        button.className = this.completed ? "btn done toggle" : "btn not-done toggle"
        icon.className = this.completed ? "fas fa-check" : "fas fa-times"

        //add an event listener to the button to toggle the class's completion state
        //binding this so we can access the task instance method inside of the callback
        button.addEventListener('click', this.toggleComplete.bind(this))

        //wrap the new elements into each other
        button.prepend(icon)
        title.innerHTML = this.title
        li.prepend(title)
        li.prepend(button)

        //return new object
        return li
    }

```
A part of this implementation that I am particularly happy with is the method on the Task class that I use to create HTML for each task, this method feels very logical and allows me to work in a very straightforward way in the rest of my code.





