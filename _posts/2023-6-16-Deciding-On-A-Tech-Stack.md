---
layout: post
title: Week 0 - Deciding on a Tech Stack
---

I decided on two other design constraints for the project. There is a word in Quebecois French for an unemployed person: "chomeur."

- **This project must be built on a "chomeur" budget.**
   
   Originally, I wanted to say a $0 budget, but there are some AWS services that I think I will need and that are cheap, which I will get into in a minute. So, the "chomeur" budget is just to spend as little as I possibly can. Planning the cloud infrastructure has been so much fun. There is a lot to learn, but luckily, I have a friend who is a senior site reliability specialist and has been giving me some fantastic DevOps and infrastructure advice. These are admittedly my weakest areas going into this project.

- **Simplicity > scalability**
   
   My target audience for this application will be a maximum of 25 regular users from the collective, plus any recruiters or random people who visit the site. I considered making this app more suitable for general use, so that other beekeeping collectives could use this system, but hosting other people is not within the "chomeur" budget. Additionally, this application needs to be developed as fast as possible because its end goal is to be a portfolio project that I can demo in interviews. I will take my time in the planning phase and hopefully come up with a badass stack that will enable me to create a full-stack application in a timely manner. But even if it goes horribly wrong, I am not going to beat myself up because this is about learning!

That being said, let's get into what my planned stack will be.

# Cloud Infrastructure

- **AWS**
  
  When comparing GCP, AWS, and Azure, it quickly became apparent that AWS is much better than its competitors when it comes to free tier offerings. Most of the services are always free, some are free for 12 months, but with the estimated amount of traffic I plan to receive for this project, it should be less than $5 per month. The organization can handle a small expense like that out of its budget, no problem, or I can just pay that out of pocket in a year's time if I have something worth maintaining (spoilers: I will).

- **Lambda Functions**
  
  Lambdas will be the crux of my backend. I will be taking a serverless approach.

- **API Gateway?**
 
  Initially, I was emphatic about using API Gateway, but the pricing after 12 months is pretty steep. As nice as it would be to have a central place to handle logging and authentication, for the sake of costs, I am going to have to forgo this service.

- **S3 Buckets**
  
  Eventually, I want users to be able to upload images for hive inspections, so this will be a cheap but necessary expense. Also, with an S3 bucket, I can securely store my Terraform state file, which brings me to...

- **Elastic Container Registry**
  
  My pipeline will be using Docker images, which I will store in ECR. It's cheap and cheerful.

Side note: I will be hosting on GitHub Pages and not using Amplify or CloudFront for cost reasons and because scalability is not necessary, but otherwise, I probably would.

# DevOps

- **Docker**
  
  The dev environment will be containerized so that collaborating on it with others will be simple. The production environment will run lambda functions in a container stored in ECR.

- **Terraform**
  
  This will be how I manage deploying my cloud setup. I chose Terraform because it is cloud-agnostic, so whatever cloud my future employer might use, I would be able to bring this skill. This will be part of my CI/CD pipeline and will make destroying the environment and saving me money easy to do, should it ever be necessary.

- **GitHub Actions**
  
  The CI/CD pipeline is still new to me, so this will be a learning experience for sure. GitHub Actions have a very good reputation, and I like that it is built into GitHub, where my code will be stored. I know that I want my code to have automated testing and deployment to AWS, but I am still figuring out the details of how to get it there. I can continue researching this and planning as I also plan my API, so I am not going to let it block me.

# Back End

- **Python**
  
  Node.js was a compelling choice, but since I am already familiar with Node, I opted to learn Python instead. Go was another contender, but I will already be using Go for Terraform, and Go seems better suited for scalability and concurrency, which are not my primary concerns. Python has a massive community, and it will be easy to handle all the things my backend will need to do with it.

- **AWS AppSync**
  
  For hosting a GraphQL server. Estimates put it around $0.10 per month after 12 months, so it's within my price range.

- **DynamoDB**
  
  It's free, in the AWS ecosystem, and NoSQL. Coming from a Mongo background, this is a no-brainer. I was originally considering Postgres, but having a database in the AWS space will make things much easier and faster.

- **AWS Cognito**
  
  For managing logging in users. There will be no sensitive data, so I am not too concerned about the obvious vulnerability of having a public API without an API Gateway for authentication. Maybe I will regret this, but since I have cost constraints, it is a necessary evil, unless I manually authenticate every lambda, but that will slow down development time, which is also bad for my end goals.

# Front End

There are still some uncertainties here, but I have plenty of time to do more research and decide because this will be the last part of the stack that enters development.

- **React?**
  
  Definitely a React app. Learning TypeScript and React are two highly desirable skills. At the moment, I am still deciding between plain React.js, Next.js, and React Native. One day, I would like to port this to an app, but I am not sure if I would need to make a separate native repository or if I can start in native and make my life easier when it comes time for app development. However, I don't need to make a decision yet because there is still so much to do before I start coding the frontend.

- **Tailwind**
  
  No Bootstrap. I want to have more flexibility, and Tailwind looks very popular, so I want to try it!

- **Sass?**
  
  I want to use Sass. Automating the compilation will be a good project on the DevOps side of things. I read somewhere that React Native has problems with Sass, though, so I need to do more research before making a commitment.

- **GraphQL**
  
  Everything I have read about GraphQL makes it a good fit for my project's needs. It speeds up development time with fewer APIs and allows me to learn new technology.

Now that I have some things decided, I can start planning my API for maintaining a meeting and hive inspection calendar.
