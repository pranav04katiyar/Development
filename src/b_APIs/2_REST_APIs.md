# REST API
REST stands for **Representational State Transfer**.
  - It is an architectural style for designing networked applications.
     > REST is an architectural style for building distributed systems based on hypermedia.
  - REST APIs are a standardized architecture for building APIs that uses HTTP methods to perform operations.
     > REST is independent of any underlying protocol and is not necessarily tied to HTTP. However, most common REST API implementations use HTTP as the application protocol, and this guide focuses on designing REST APIs for HTTP.
  
     > - A primary advantage of REST over HTTP is that it uses open standards, and does not bind the implementation of the API or the client applications to any specific implementation. 
       >  - For example, a REST web service could be written in ASP.NET, and client applications can use any language or toolset that can generate HTTP requests and parse HTTP responses.
  - REST defines a set of functions like GET, PUT, DELETE, etc. that clients can use to access server data.
  - The main feature of REST API is statelessness.
     > - Statelessness means that servers do not save client data between requests
     > - Client requests to the server are similar to URLs you type in your browser to visit a website.
     > - The response from the server is plain data, without the typical graphical rendering of a web page.
  - These are the most popular and flexible APIs found on the web today.
  
### Some main design principles of RESTful APIs using HTTP:
- REST APIs are designed around resources, which are any kind of object, data, or service that can be accessed by the client.
- The type of action an API is doing should not be part of the URI. Rather, the action should be part of the HTTP method type. 
    > For example, a URL that includes the action to be taken is not RESTful:
    > ```
    > https://adventure-works.com/create-order
    > ```
  - Every API is an action on one of the models.
  - The tye of action should be ideally specified by the HTTP method type instead of via a verb in the URl.
      > - There are multiple HTTP methods that can be used to perform different actions on the same resource, like GET, POST, PUT, PATCH, DELETE, etc. which are discussed below.
  - A resource has an identifier, which is a URL that uniquely identifies that resource. 
      > For example, the URI for a particular customer order might be:
      >  ```
      >  https://adventure-works.com/orders/1
      >  ```
  - Clients interact with a service by exchanging representations of resources. Many web APIs use JSON as the exchange format.
      > For example, a GET request to the URI listed above might return this response body:
      > ```
      > {"orderId":1,"orderValue":99.90,"productId":1,"quantity":1}
      > ```

  - REST APIs use a uniform interface, which helps to decouple the client and service implementations. 
    >  - For REST APIs built on HTTP, the uniform interface includes using standard HTTP verbs to perform operations on resources. 
    > 
    >  - ***The most common operations are GET, POST, PUT, PATCH, and DELETE.***
    >    - GET retrieves a representation of the resource at the specified URI. The body of the response message contains the details of the requested resource.
    >    - POST creates a new resource at the specified URI. The body of the request message provides the details of the new resource. Note that POST can also be used to trigger operations that don't actually create resources.
    >    - PUT either creates or replaces the resource at the specified URI. The body of the request message specifies the resource to be created or updated.
    >    - PATCH performs a partial update of a resource. The request body specifies the set of changes to apply to the resource.
    >    - DELETE removes the resource at the specified URI.
    > 
    >  - ***The differences between POST, PUT, and PATCH can be confusing:***
    >    - A POST request creates a resource. The server assigns a URI for the new resource, and returns that URI to the client. 
    >     - In the REST model, you frequently apply POST requests to collections. 
    >     - The new resource is added to the collection. 
    >     - A POST request can also be used to submit data for processing to an existing resource, without any new resource being created.
    >    - A PUT request creates a resource or updates an existing resource. The client specifies the URI for the resource. 
    >     - The request body contains a complete representation of the resource. 
    >     - If a resource with this URI already exists, it is replaced. 
    >     - Otherwise a new resource is created, if the server supports doing so.
    >     - PUT requests are most frequently applied to resources that are individual items, such as a specific customer, rather than collections. A server might support updates but not creation via PUT. Whether to support creation via PUT depends on whether the client can meaningfully assign a URI to a resource before it exists. 
    >     - If not, then use POST to create resources and PUT or PATCH to update.
    >    - A PATCH request performs a partial update to an existing resource. The client specifies the URI for the resource. 
    >     - The request body specifies a set of changes to apply to the resource.
    >     - This can be more efficient than using PUT, because the client only sends the changes, not the entire representation of the resource. 
    >     - Technically PATCH can also create a new resource (by specifying a set of updates to a "null" resource), if the server supports this.
    >    
    >   > - PUT requests must be idempotent. 
    >   >   - If a client submits the same PUT request multiple times, the results should always be the same (the same resource will be modified with the same values).
    >   >   - POST and PATCH requests are not guaranteed to be idempotent.
