---
layout: post
title: Week 4 - One Step Forward
---

This week I started designing the web layout of buzzhub, and made some significant progress with the API. I made some design decisions with forced me to pivot from the code that I had already written, but I think the changes made will pay off in the long run.

## UX
I made a page outline in FigmaJam and had a review meeting with a collaborator who is a UX professional. We refined the design that I had made and found ways to revise some pages to make others redundant. He also talked me out of implementing a dark mode, as he made the good point that it will double the amount of UI design work to do which could crucially be spent on other parts of the project to get us to a functional state. We are going to have another meeting this week, so for now I have opted to get focused on building out the API.

## Front End
I started using the Mantine UI library to bring some pre-built components into my project. I like that they are easily extensible, as I plan to restyle them with Tailwind once the UI is locked down. I have a menu and a calendar working in my staging environment, dev.buzzhub.cc . I want to try to get prerendering working on the content that I have now, as well as moving logic outside of the UI components that I have writted and passing them in as props. I will be focusing on getting front end unit testing set up next.

## Back End
The back end saw significant rewrites this week. I decided not to track calendar events in my dynamoDB database, and instead pull them from the trello API to make use of the system that we are already using in my beekeeping club. I was seeing issues already where when we changed dates in trello, data in my database was out of sync, so I decided it made more sense to keep a single source of truth AKA the trello boards. I am working on user registration API routes now.

## DevOps
I added some jobs in my pipeline to prevent pull requests to main from branches other than develop, after making a few 2am mistakes 🫢. I also moved deploying lambda function code and environment variables into my github actions instead of trying to manage it in my terraform config. This week I need to improve my pipeline to allow separate deployments to prod and dev depending on whether the target is main or develop branch.

## Cloud
I have created a cognito user pool for my dev environment, and set up the aws simple email service for user self registration and password recovery. I still have a few resources that exist outside of my terraform config that need to be migrated in.
