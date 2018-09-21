---
layout: post
title:      "Reader's Club "
date:       2018-09-21 22:08:08 +0000
permalink:  readers_club
---


It’s a big milestone to get to this point of working on my second portfolio project. I am very pleased with what I have learned and how much I have accomplished to this point.  To start off this project, I built out the skeleton of my app using Corneal , a gem that was created by a former flatiron grad and mimics the skeletons of MVC structures used in the lab exercise in the Sinatra session. 

My app functions as a reading list that users create to keep track of his/her favorite books and the user can also edit, update his/her own reading list which  satisfied with the CRUD requirement of the assignment. 

I think the most important aspect of this project is session management - whether the user is logged in and which user is logged in, that ensures that only the logged in user can update or edit the reading list.  When the user creates an account and chooses a password, the password is secured by a gem called bcrypt, which will synchronize the password. This implementation secures the user by preventing the password to be seen by anybody other than the user. Even the administrator of the app can only see the encrypted version of the password. This is an important back-end functionality of an application.

During the process of working on the Sinatra app I was able to review what has been covered in the curriculum so far. I also learned some new concepts like `has_and_belongs_to_many` associations between models while researching how to deploy certain features. I truly learned a lot while working on this project. 
