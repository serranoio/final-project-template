# Your final project name goes here
Accential 

(Accounting + Financial = Accential)
# Your team member names and uic emails go here
dserra22@uic.edu

# Your GitHub repository link goes here

Main repo:

https://github.com/serranoio/accential


This is the frontend sub-repo of accential.

frontend:
https://github.com/serranoio/frontend


## What does your application do?

Converts a financial statement pdf into an accounting statement HTML document which can also be downloaded as a pdf.

To automate an accountant's job ;).


## What makes it different than a CRUD app? I.e., what functionality does it provide that is not just a user interface layer on top of a database of user information,and the ability to view / add to / change that information?

HMMMMMMMMMMM...

Converting an entire financial statement into an accounting statement is what it does. Eventually, we'll include an sql backend which saves the converted pdf's and users with their converted pdf's.

At the beginning, there will be no CRUD. the goal will be to parse the financial statement.

Here's my plan:

I already started the frontend, you can see the hero page in github. It is written in Rust & Leptos (framework using signals to create reactivity) which compiles down into webassembly and is then ran in the browser.

The frontend I am creating will honestly not be that much. Just a very sexy landing page with barely any interaction. The main entree of my project is in the backend:

To create the converter, I will be utilizing RabbitMQ in golang to implement Pub/Sub. My *goal* is to split up the tasks of the converter into microservices, all being connected by the message broker. The end result of this should be data that can be used to create an HTML document. I plan on using hydration to create the html document. THIS time, I will use Lit Element as my Javascript framework, and have the data be constructed from golang. 

This plan does not utilize ANY CRUD but CRUD is the next step. It's a priority to get the functionality done first.

Can't I just create one service to handle everything?
Yes, but no. It has to be modern and scalable. 

## What security and privacy concerns do you expect you (as developers) or your users to have with this application?

The exposed APIs on the backend. I want to be sure to make them private.
  - I think I am going to have a microservice dedicated to handling http/pub/sub requests. It might be that I can just set the CORS policy to only accept my frontend :P and boom I'm good. The other microservices should run on the same localhost (server) so their API's *shouldn't* be exposed to the outside world. I don't know. It's time to put in research.

Other than that, once I get to CRUD (which is barely in my mind) User Auth is a BIG one.

### This repository

This repository has a package.json that functions as a blank shell that gets full credit if you turn it in to the gradescope autograder. We will not be using the autograder in any way to actually evaluate your project, it is just there to keep track of your initial submission.

We recommend that you use this repository for your final project code. This will allow you to ask questions on Piazza and get help from the TAs and instructors. Adding a real linter, type checker, etc, based on our other examples would be a good idea.


