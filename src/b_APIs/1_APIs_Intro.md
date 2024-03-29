# API
API stands for Application Programming Interface.

1. Application refers to any software with a distinct function.
2. Interface can be thought of as a contract of service between two applications.

## What is an API?
APIs are mechanisms that enable two software components to communicate with each other using a set of definitions and protocols.
These are defined contracts/set of rules/methods which allow one application to interact with another, by exposing the functionalities.
> - They define all the details for communication between different components and how a particular method/endpoint should respond when they are called.
> - API calls are transfer of state(Data) of different objects between different applications.
>  - For example:
>    - The weather bureau’s software system contains daily weather data & the weather app on your phone “talks” to this system via APIs to shows you daily weather updates on your phone.
>    - when you use a mobile application to book a cab, the application sends your location to the server, which then sends the cab to your location.

> Most modern web applications expose APIs that clients can use to interact with the application. A well-designed web API should aim to support:
>   - Platform independence: 
>     - Any client should be able to call the API, regardless of how the API is implemented internally.
>     - This requires using standard protocols, and having a mechanism whereby the client and the web service can agree on the format of the data to exchange.
>   - Service evolution:
>     - The web API should be able to evolve and add functionality independently from client applications.
>     - As the API evolves, existing client applications should continue to function without modification. 
>     - All functionality should be discoverable so that client applications can fully use it.

> This guidance describes issues that you should consider when designing a web API.

## How does an API work?
- APIs work by sending requests to a server and receiving responses back.
- The application sending the request is called the ***client***, and the application sending the response is called the ***server***.
- There are different types of APIs, such as REST, SOAP, WebSocket, RPC, GraphQL etc., each with its own set of rules and protocols.

1. **REST APIs**: 
    > - REST stands for **Representational State Transfer**. 
    > - It is an architectural style for designing networked applications. 
    > - REST APIs are a standardized architecture for building APIs that uses HTTP methods to perform operations.
    > - REST defines a set of functions like GET, PUT, DELETE, etc. that clients can use to access server data.
    > - The main feature of REST API is statelessness.
    >   - Statelessness means that servers do not save client data between requests
    >   - Client requests to the server are similar to URLs you type in your browser to visit a website. 
    >   - The response from the server is plain data, without the typical graphical rendering of a web page.
    > - These are the most popular and flexible APIs found on the web today.
2. **SOAP APIs**:
    > - SOAP stands for **Simple Object Access Protocol**.
    > - It is a protocol that uses XML for sending and receiving messages between applications.
    > - It is a protocol for accessing web services. 
    > - This is a less flexible API that was more popular in the past.
3. **WebSocket APIs**: 
    > - WebSocket is a communication protocol that provides full-duplex (two-way) communication channels over a single TCP connection. 
    > - It uses JSON objects to pass data.
    > - The server can send callback messages to connected clients, making it more efficient than REST API.
    > - It is used for real-time communication between a client and a server.
4. **RPC APIs**: 
    > - RPC stands for **Remote Procedure Call**. 
    > - It is a protocol that one program can use to request a service from a program located on another computer in a network without having to understand the network's details
    > - The client completes a function (or procedure) on the server, and the server sends the output back to the client.
5. **GraphQL APIs**: 
    > - GraphQL is a query language for APIs and a runtime for executing those queries by using a type system you define for your data. 
    > - It was developed by Facebook in 2012 and released as an open-source project in 2015.

## Whats a web API?
- A Web API or Web Service API is an application processing interface between a web server and web browser.
> - All web services are APIs but not all APIs are web services. 
> - REST API is a special type of Web API that uses the standard architectural style explained above.

> The different terms around APIs, like Java API or service APIs, exist because historically, APIs were created before the world wide web.
> Modern web APIs are REST APIs and the terms can be used interchangeably.
 
## What are API Integrations?
API integrations are software components that automatically update data between clients and servers. 
> - Some examples of API integrations are 
>  - when automatic data sync to the cloud from your phone image gallery, or 
>  - the time and date automatically sync on your laptop when you travel to another time zone.

## Types of APIs
1. **Open APIs**: 
    - Open APIs are publicly available for developers to use. They are also known as external APIs.
    > - They are used to enable third-party developers to access the functionality of a system.
    > - For example, Google Maps API, Twitter API, etc.
2. **Internal APIs**: 
    - Internal APIs are used within a company to improve its own products and services. They are also known as private APIs.
    > - They are used to improve the internal efficiency of a company.
    > - For example, Amazon’s internal APIs for its website.
3. **Partner APIs**: 
    - Partner APIs are used to provide access to a company’s business partners.
    > - They are used to improve the services provided to the company’s partners.
    > - For example, Salesforce’s partner APIs.
4. **Composite APIs**: 
    - Composite APIs are APIs that combine multiple data and service APIs.
    > - They are used to provide a single point of access to information.
    > - For example, a weather API that combines data from multiple weather sources.

## What are API Endpoints?
- API endpoints are the final touchpoints in the API communication system. 
- These include server URLs, services, and other specific digital locations from where information is sent and received between systems. 

## Why are API Endpoints important?
- API endpoints are critical to enterprises for two main reasons:
> 1. Security: API endpoints make the system vulnerable to attack. API monitoring is crucial for preventing misuse.
> 2. Performance: API endpoints, especially high traffic ones, can cause bottlenecks and affect system performance.
 
