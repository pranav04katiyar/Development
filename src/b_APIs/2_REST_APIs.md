# REST API
REST is an architectural style for building distributed systems based on hypermedia. 

- REST is independent of any underlying protocol and is not necessarily tied to HTTP. 

- However, most common REST API implementations use HTTP as the application protocol, and this guide focuses on designing REST APIs for HTTP.

  - A primary advantage of REST over HTTP is that it uses open standards, and does not bind the implementation of the API or the client applications to any specific implementation. 
    > For example, a REST web service could be written in ASP.NET, and client applications can use any language or toolset that can generate HTTP requests and parse HTTP responses.
    
- Here are some of the main design principles of RESTful APIs using HTTP:
    > - REST APIs are designed around resources, which are any kind of object, data, or service that can be accessed by the client.
    > - A resource has an identifier, which is a URI that uniquely identifies that resource. For example, the URI for a particular customer order might be:
    >  ```
    >  https://adventure-works.com/orders/1
    >  ```
    > - Clients interact with a service by exchanging representations of resources. Many web APIs use JSON as the exchange format.
    >   - For example, a GET request to the URI listed above might return this response body:
    >     ```
    >     {"orderId":1,"orderValue":99.90,"productId":1,"quantity":1}
    >     ```
    > - REST APIs use a uniform interface, which helps to decouple the client and service implementations. 
    >   - For REST APIs built on HTTP, the uniform interface includes using standard HTTP verbs to perform operations on resources. 
    >   - The most common operations are GET, POST, PUT, PATCH, and DELETE.
    >     - GET retrieves a representation of the resource at the specified URI. The body of the response message contains the details of the requested resource.
    >     - POST creates a new resource at the specified URI. The body of the request message provides the details of the new resource. Note that POST can also be used to trigger operations that don't actually create resources.
    >     - PUT either creates or replaces the resource at the specified URI. The body of the request message specifies the resource to be created or updated.
    >     - PATCH performs a partial update of a resource. The request body specifies the set of changes to apply to the resource.
    >     - DELETE removes the resource at the specified URI.
