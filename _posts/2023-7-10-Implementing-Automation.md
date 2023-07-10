---
layout: post
title: Week 3 - Implementing Automation
---

This week I spent most of my time setting up my CI/CD pipelines and creating test cases for my existing code. I also onboarded my first contributor, another developer, and showed her a tour of the codebase and helped her create her first pull request! Without further ado let’s break the week down by the 5 usual categories

## UX
I had some difficulties here with purchasing a domain for my project. I bought one on google domains but ran into some issues when trying to use it in aws amplify. I decided to just purchase a new domain in aws route 53 to save myself the headache of trying to configure something that is supposed to be easy. By the time this post is live, www.buzzhub.cc should be live. This week I am going to be focusing a lot more on the UX and UI, so that I can start building more front end components and having smaller tasks to delegate to other devs.

## Front End
This week I spent some time learning about tailwind, I plan to incorporate it going forward when building and styling components. I plan to spend some more time figuring out a good plan for testing my front end next. The plan right now is to use jest or cypress, but I need to do more research into both before making a final decision.

## Back End
Back end has test cases! Now that I have learned to use python and mock the db, I plan to write tests as I create new features, test driven development for the win! I am running into a problem with having multiple sources of truth in the calendar. Our org currently is using a google calendar to keep track of meetings, and I fear that my original plan of keeping calendar events in a dynamodb table is going to cause problems as we try to manage 2 calendars. I am going to try to pivot this week and instead use the google calendar API to integrate it into buzzhub.

## DevOps
I made some great progress in this category! CI pipelines exist in all my github repos, and they all have fully functional linters. Already they have caught a bunch of code formatting mistakes and made suggestions to refactor deprecated functionalities, I am glad to have them as a guard rail going forward. Additionally, I have my back end api’s test cases being automatically run, now I just need to do the same for my front end. The CD side of things is handled out of the box with aws amplify, I just push a change to the main branch of my repository and it will handle building and deploying. It is possible to add test cases to the cd pipeline, so down the line I may look into adding end-to-end tests while deploying.

## Cloud
I set up IAM roles for my developers, in terraform of course, and am able to provision and delete new users with all their needed permissions by adding or removing their name to a file in my terraform config. I need to learn next how to add existing resources to my terraform state, as there are a few things I created when getting started such as my terraform state bucket, my amplify app, and my personal IAM user, that I would rather not delete and recreate. Plus migrating it will be a good skill to have down the line if ever I were working for a company that wanted to implement IaC.
