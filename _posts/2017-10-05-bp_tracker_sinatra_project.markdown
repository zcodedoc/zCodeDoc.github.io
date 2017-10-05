---
layout: post
title:      "BP Tracker (Sinatra Project)"
date:       2017-10-05 12:05:29 +0000
permalink:  bp_tracker_sinatra_project
---


With each of these portfolio projects I try to build an application that can be used in the real world. The inspiration for this project came from my father. The blood pressure tracker or BP Tracker as I have name my app it's supposed to help people keep track of their blood pressure in a convenient way.

So with that being said, I'll quickly explain how to use my website. A new user must create a login and profile, both of which require all fields to be filled out. The application calculates the users age from their DOB and it's displayed on their profile page. For the profile section I tried to emulate a doctor's office form.

In order to add a new blood pressure reading, the user can click the button ‘add reading’. This takes the user to a form that asks for a date, time, systolic and diastolic pressure, as well as a pulse. I included a section for notes if the user wanted to add a comment. On the table that is displayed to the user, I attached in a 'category' column that is also computer calculated. It has two functions. First. it verifies that the user BP is valid, or humanly possible. And informs the user of what category their reading places their blood pressure at to help them figure out what kind of treatment they may need. 

And that's about it! I did add in search fields, which allow the user to lookup/view specific sets of dates (based from their input). This enables the user to be able to print a report to take to their doctor's office if they wanted.

For this project I would say the number one part of construction I struggled with was working with the join table. I have done a lot of work with Activerecord associations on everything except join tables. Nevertheless, my dad pushed me to test my knowledge and learn new things. The second time consuming issue, was working with HTML. I have gone through the first section of JavaScript and that knowledge and Google save my life.

One of my favorite parts of code I utilized was definitely Activerecords usage of 'reference' which allows the use of dependents destroy'. This made creating my delete functionality a lot easier. And I also learned something new. Additionally, I really like the applications 'search' ability. I think it makes it similar to 'real world' websites.

So, reader if you know someone with high blood pressure or you yourself want to keep track of your BP checkout my software!
