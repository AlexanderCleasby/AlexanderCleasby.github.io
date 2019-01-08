---
layout: post
title:      "CLI Project"
date:       2019-01-08 18:17:48 +0000
permalink:  cli_project
---


The first project in the Flatiron curriculum was to write a CLI that displays data from the internet using Ruby.  The project was pretty fun to go through and I feel I did become a better coder as a result.

The curriculum to this point prepared us very well for this project and at least for my project all the methods on their own were pretty easy to set up.  I do however feel the important lessong here is to reduce technical debt by isolating diffrent concerns.  I actually started this assignment a while ago then didn't pick it up again for a good while, but when I was doing the assignment directly precceeding this project, which I assume we are meant to be a model for this project I got the idea that we are meant to split each concern into classes more finely than I did as a knee jerk.  For instance I had puts and gets in the body of each class whereas what I ended up doing by the end was allocating all the user input and log output into it's own "CLI" class.  Disciplining yourself like this is pretty clearly the better way to go about this problem as you could imagine as your codebase grows finding all these puts and gets spread around every class would be really tiring.

All in all I feel that this project was a good learning experince.
