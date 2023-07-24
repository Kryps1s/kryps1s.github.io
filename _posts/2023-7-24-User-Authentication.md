---
layout: post
title: Week 5 - User Authentication
---

This week, my focus was on setting up user authentication with an AWS Cognito user pool and implementing a login and sign-up form for the site.

## UX
The UI for the site is still in progress, and my UI designer is working on creating wireframes. Part of me was eager to get more involved in the UI creation to gain experience using tools like Figma. However, I don't want to micromanage my contributors, and since I already have many other tasks on my plate, I have decided to delegate this aspect of the project for the time being. I am actively searching for a talented artist who can assist me in creating a logo (for free).

## Front End
I have created a sign-up form as well as a login form within the application. I onboarded a former coworker and assigned him some tasks to improve the form validations and selects. I have realized that I need to be much more descriptive in my Kanban stories when I assign them to contributors. This way, they won't waste their time working on something that doesn't align with my vision due to unclear instructions. I am starting to regret using Next.js for this project because I might not be able to fully utilize its great SSR and caching abilities. That being said I think the framework is fantastic, even if not perfectly suited to my project, so I am still enjoying getting experience with it.

## Back End
In the back end, I have created new routes for logging in and creating users, getting Trello members for linking their accounts to Buzzhub, and test cases for all of the above. The next step is to make the beekeeping job note-taker, which will be my first API route that requires authentication.

## DevOps
My pipeline is starting to get a bit cumbersome. I have two YAML files, one for dev and one for prod, which deploy my lambda functions along with their required env variables. I am currently having to add each lambda manually to each file, which is obviously not the best practice. I have looked into creating some type of template task for deploying a lambda, and then just calling the template task and passing in the environment and environment variables required, but I haven't managed to successfully implement it yet. It is definitely on my radar but not my highest priority for now.

## Cloud
I have added my Cognito user pools, but I'm facing serious issues with my AWS Simple Email Service. AWS is refusing to take my account out of the dev sandbox, which means I will not be able to send confirmation code emails to my users. I am having to manually approve their accounts for now, which is not good at all, but unfortunately, the only option I have at my disposal until I can resolve things with AWS. I also imported a few resources that I had provisioned outside of my Terraform state, which came in handy when it was time to recreate them for my production environment.
