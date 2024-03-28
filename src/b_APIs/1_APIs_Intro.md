# API
API stands for Application Programming Interface.

1. Application refers to any software with a distinct function.
2. Interface can be thought of as a contract of service between two applications.

## What is an API?
> - APIs are mechanisms that enable two software components to communicate with each other using a set of definitions and protocols.
> - These are defined contracts/set of rules/methods which allow one application to interact with another, by exposing the functionalities.
> - They define all the details for communication between different components and how a particular method/endpoint should respond when they are called.
> - API calls are transfer of state(Data) of different objects between different applications.
>  - For example:
>    - The weather bureau’s software system contains daily weather data & the weather app on your phone “talks” to this system via APIs to shows you daily weather updates on your phone.
>    - when you use a mobile application to book a cab, the application sends your location to the server, which then sends the cab to your location.

## How does an API work?
- APIs work by sending requests to a server and receiving responses back.
- The application sending the request is called the ***client***, and the application sending the response is called the ***server***.
- There are different types of APIs, such as REST, SOAP, WebSocket, RPC, GraphQL etc., each with its own set of rules and protocols.

1. **REST APIs**: 
    > - REST stands for **Representational State Transfer**. 
    > - It is an architectural style for designing networked applications. 
    > - REST APIs are a standardized architecture for building APIs that uses HTTP methods to perform operations.
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