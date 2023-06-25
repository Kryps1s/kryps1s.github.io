---
layout: post
title: Week 1 - Building my Infrastructure
---



I've set up a Kanban board with some epics to keep track of my progress and what needs to be done. I've divided the tasks into five categories:

## UX

I pitched the idea to my stakeholders and gathered initial feedback on the desired features they would like to see first. This feedback will help me create a roadmap for my features. Next, I plan to create a few user personas and develop wireframes for the initial version.

## Front End

I've read all of the documentation to brush up on Typescript, React, Next.js, Sass, and Tailwind. I have completed the tic-tac-toe and blog projects from the React and Next.js documentation websites. Next.js offers impressive built-in features, such as hybrid rendering, which allows for server-side rendering of some pages while others are automatically rendered at build time and served over a CDN (static site rendering). The development environment also provides convenient features like hot reloading. I have created a few prototype components without styling for the initial launch. The next steps include connecting it to my backend, deployment, adding test cases, and implementing automation.

- **Radix Primitives:** I am eager to incorporate these simple unstyled UI components into my front end. They come with excellent accessibility features out of the box and have a robust API documentation, making them easy to use to their full potential. Since they are not overly styled, we can customize their appearance using Tailwind.
- **Radix Colors:** These color palettes will complement the design we have in mind, including a palette specifically designed for dark mode, which is essential for any application.

## Back End

I have created the table and written and deployed a basic Python lambda function to write to my database. I have developed a GraphQL API (and read GraphQL's documentation) to perform basic CRUD operations. Currently, I am working on configuring the actual API to connect with my development database. I am facing some challenges in configuring it to directly access the DynamoDB tables with VTL resolver functions, so my next approach will involve using Python scripts with lambda. I have gained a deeper understanding of the differences between NoSQL and relational databases and I am embracing denormalization, opting to manage my Calendar using a single table. Initially, I had taken a very relational approach with multiple tables, but I realized this was not aligned with how NoSQL data should be handled. Therefore, I went back to the drawing board, and I believe my revised design is much improved.

## DevOps

As of now, there isn't much progress in this area since I need to have code before I can integrate or deploy. My plan is to manually launch the first version, then add test cases and gradually establish the pipeline with subsequent pushes.

## Cloud

I have made significant progress in building my cloud setup using Terraform. Infrastructure as Code (IaC) has proven to be convenient, simplifying the management of provisioned resources compared to using the cloud GUI. I am aiming to incorporate this into a CD pipeline, automating this part of the build process. I am also utilizing variables to keep my code DRY (Don't Repeat Yourself). For example, one database can be named "db-{$terraform.workspace}," ensuring consistency between the development and production environments. Additionally, I can modify the quantity of provisioned resources for each environment using environment variables, allowing for potential scalability of the production environment in the future.
