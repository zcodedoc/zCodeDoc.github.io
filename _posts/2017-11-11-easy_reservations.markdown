---
layout: post
title:      "Easy Reservations"
date:       2017-11-11 10:22:49 -0500
permalink:  easy_reservations
---


WOW! Rails!!! That's exactly how I feel right now. This project has been quite a journey, from playing with css to coding out the a fulling functional nest attribute, without the use of that AWESOME Rails macro 'accepts_nested_attributes.' **Sigh** Coding is difficult and yet so rewarding. It's that challenging workout that everyone dreads starting, but at the end feel great that they completed. 

And I guess, that's me now =D

For this project, I decided to build a hotel reservation website, called *Easy Reservations*. It displays several hotels and allows the user to view and reserve a variety of rooms. I chose this as my project because for about a half of a year I worked in the hotel industry.  I always try to somehow connect my programs with my life. I tried to build my app similar to other reservation sites and allow people to have access to almost everything, except creating a reservation. Hence, where the log in and registration systems come into play. However, because of Learn's requirement to have ' a nested form that writes to an associated model through a custom attribute writer, ' my users are also required to have a home address, even the ones who register through GitHub. If a user doesn't have a home address they can't make a reservation, even if their logged in. I added this because having a home address and phone number were two important pieces of information the hotel always wanted. Other then these two extra steps, I think my app is pretty standard. But, my prices are quite phenomenal and my taxes are cheaper then most! ;+D

One of the main things I struggled with was getting all the code that works with updating my room inventory to work properly. This is partially because I forgot about this aspect until I was wrapping up my program. But, through debugging and stepping through almost every step in the reservation process, I some how figured it out.  ;+)  Also, figuring out how to update my nested attribute was quite a doozy as well. Creating the custom writer wasn't hard because Learn did a good job explaining how to do this in past labs, and my B.F.F., Google helped out with making the form. And so that left only the 'updating' aspects' as the unknown abyss. This definitely took A LOT of Googling around and reading, StackOverflows, APIDocks and scouring RailsGuides to understand and code this out. The third incredibly 'semi'-new feature of my app that I wanted to highlight is my usage of virtual attributes, if those don't showcase Ruby, I'm not sure what will! At first my reservation code consisted of getter & setter methods for almost the entire reservation form, when my wonderful dad reminded me of those awesome Ruby attribute accessors! Talk about a quick code clean up!

To end on a high note, I must mention my validations. I do have some standard ones, that test for presence. However, I also built out some custom validations that work with dates and time, and o'boy did that open-up a whole new can of worms! Nevertheless, now that their functioning appropriately, I couldn't be prouder of my struggle!

So, hey, whenever you have time, check out my reservation app, it's simple but nice and remember I've got KILLER prices!!! :-D

