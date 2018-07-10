# MICROSERVICES ARCHITECTURE
* **An alternative pattern that addresses the limitations of the monolithic architecture**.


## Context

You are developing a **server-side enterprise application**. It must support a variety of different clients including desktop browsers, mobile browsers and native mobile applications. The application might also expose an API for 3rd parties to consume. It might also integrate with other applications via either web services or a message broker. The application handles requests (HTTP requests and messages) by executing business logic; accessing a database; exchanging messages with other systems; and returning a HTML/JSON/XML response. There are logical components corresponding to different functional areas of the application.

## Problem

What’s the application’s deployment architecture?


## Forces

* There is a team of developers working on the application
* New team members must quickly become productive
* The application must be easy to understand and modify
* You want to practice continuous deployment of the application
* You must run multiple copies of the application on multiple machines in order to satisfy scalability and availability requirements
* You want to take advantage of emerging technologies (frameworks, programming languages, etc)


## Solution(A)

**Build an application with a monolithic architecture**
![alt text](http://microservices.io/i/DecomposingApplications.011.jpg)

### Pros Of Resulting Context
* Simple to develop
* Simple to deploy
* Simple to scale 

**However, once the application becomes large and the team grows in size, this approach has a number of drawbacks that become increasingly significant:**

### Cons 
* The large monolithic code base intimidates developers, especially ones who are new to the team.
* Overloaded IDE
* Overloaded web container 
* Continuous deployment is difficult 
* Scaling the application can be difficult
* Obstacle to scaling development
* Requires a long-term commitment to a technology stack 

## Solution(B)

Define an architecture that structures the application as a set of loosely coupled, collaborating services. This approach corresponds to the Y-axis of the [Scale Cube](http://microservices.io/articles/scalecube.html). Each service implements a set of narrowly, related functions. For example, an application might consist of services such as the order management service, the customer management service etc.

Services communicate using either synchronous protocols such as HTTP/REST or asynchronous protocols such as AMQP(Advanced Message Queuing Protocol). Services can be developed and deployed independently of one another. Each service has its own database in order to be decoupled from other services. Data consistency between services is maintained using the [Saga pattern](http://microservices.io/patterns/data/saga.html).

**Example**


![alt text](http://microservices.io/i/Microservice_Architecture.png)
