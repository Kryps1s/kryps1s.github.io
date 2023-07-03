---
layout: post
title: Week 2 - Buzzhub is Live!
---

I've successfully deployed my project to the production environment! [Check it out here](https://main.d366n82ch0ba7s.amplifyapp.com/). I definitely need to purchasing a better domain 😅. I have accomplished a lot in the past week but there's still lots more to do. Let's break it down:

## UX
I came across a fantastic article on Medium about a guy who redesigned the McDonald's app for fun. [Here's the link](https://medium.com/@bungaazhararosalisa/mcdonalds-mobile-app-redesign-ui-ux-case-study-861dd2511742). I plan to draw inspiration from his work to create design components and identify pain points in my biggest competitor's product, ApiaryBook. Designing the user interface is one of my primary concerns in the upcoming week, closely followed by testing, which I will discuss further in the devops section.

## Front End
The home page is now live with server-side rendering and caching, but there's still room for improvement. I particularly enjoy using TypeScript and the development tooling it provides. The ability to determine function expectations and outputs helps to speed up development as I continue expanding the platform.

## Back End
I have a few modifications to make in my GraphQL schema to retrieve the precise data needed for the homepage. Additionally, I need to write tests and eventually implement a login system to authenticate requests before enabling the creation, editing, and deletion of meetings.

## DevOps
Testing is crucial, and I must add automated tests to both the front end and back end repositories. Moving forward, I won't check in any new features or functionalities without attached test cases.

## Cloud
I received a billing of $0.03 for some unintentional CloudWatch alerts I set up during testing. I promptly disabled them and will monitor the situation closely. Apart from that, I need to transfer some Lambda functions I created and Amplify hosting while testing my front end and back end code into Terraform.
