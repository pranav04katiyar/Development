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
  - REST APIs are the most popular and flexible APIs found on the web today.
  
### Some main design principles of RESTful APIs using HTTP:
- REST APIs are designed around resources, which are any kind of object, data, or service that can be accessed by the client.
    > - Resources can be: 
    >   - Collections of resources (like a list of users, a list of products, etc.)
    >   - Individual or a single attribute of a resource (like details of a single user, an individual product, etc.)
    > - Think of every resource type as a folder in a file system, and every entity as a file in that folder.
    >    - > For example, a collection of users can be considered as a folder(/users) and each user can be considered as a file(/users/{id}).
- REST APIs should be stateless. This allows to build APIs that are easy to maintain, stable and can scale easily.
    > - The next request should not be dependent on any previous request. Each request from a client must contain all the information required by the server to fulfill the request.
    > - No API should maintain any data on an individual server.
    >   - In FTP systems, the server maintains the state of the client, because there was a 1:1 connection between the client and the server.
    >   - In REST APIs, the server does not maintain any state of the client, as there are different requests coming from different clients can be routed to different servers.
    >   - Each request of HTTP is independently routed, i.e, independent of the previous request, so it is not possible to maintain the state of the client in the server.
    > - Also, the server must not store any client state between requests. 
    > - This constraint enables the server to scale and recover from partial failures more effectively.
- The type of action an API is doing should not be part of the URL. Rather, the action should be part of the HTTP method type. 
    > For example, a URL that includes the action to be taken is not RESTful:
    > ```
    > https://adventure-works.com/create-order
    > ```
    > - Every API is an action on one of the models.
    > - The type of action should be ideally specified by the HTTP method type instead of via a verb in the URL.
    >   - There are multiple HTTP methods that can be used to perform different actions on the same resource, like GET, POST, PUT, PATCH, DELETE, etc. which are discussed below.
- No need to have 1:1 mapping between the API and the database tables. 
    > - The API can be designed in such a way that it can fetch data from multiple databases and return it to the client.
    > - The API can also be designed in such a way that it can fetch data from multiple tables and return it to the client.
    > - The API can also be designed in such a way that it can fetch data from multiple microservices and return it to the client.
- Don't build Chatty APIs
    > - Chatty APIs are APIs that require multiple requests to get the required data.
    > - Chatty APIs are not efficient and can be slow as they don't return all relevant data in a single request.
- A resource has an identifier, which is a URL that uniquely identifies that resource. 
    > For example, the URI for a particular customer order might be:
    >  ```
    >  https://adventure-works.com/orders/1
    >  ```
- REST has no constraint with respect to datatype of response.
    >  - Clients interact with a service by exchanging representations of resources. Many web APIs use JSON as the exchange format.
    >  For example, a GET request to the URI listed above might return this response body:
    >  ```
    >  {"orderId":1,"orderValue":99.90,"productId":1,"quantity":1}
    >  ```

    >  The most popular datatype of responses are:
    >  1. JSON (JS Object Notation): 
    >    - > Response has details as key-value pairs. Is the most recommended standard of response datatype.
    >    - > It used less size as the response contains the info. in lesser characters.
    >  2. XML: Has larger size due to boiler code and more characters in response body.
    >  3. Protobuf: Has the smallest size among the 3.

- REST APIs use a uniform interface, which helps to decouple the client and service implementations. 
    > - For REST APIs built on HTTP, the uniform interface includes using standard HTTP verbs to perform operations on resources. 

### HTTP Methods:
- ***The most common operations are GET, POST, PUT, PATCH, and DELETE.***
    - **GET Method:**
        > GET retrieves a representation of the resource at the specified URI. The body of the response message contains the details of the requested resource.
    - **POST Method:**
        > POST creates a new resource at the specified URL. The body of the request message provides the details of the new resource. Note that POST can also be used to trigger operations that don't actually create resources.
    - **PUT Method:**
        > PUT either creates or replaces the resource at the specified URL. The body of the request message specifies the resource to be created or updated.
    - **PATCH Method:**
        > PATCH performs a partial update of a resource. The request body specifies the set of changes to apply to the resource.
    - **DELETE Method:**
        > DELETE removes the resource at the specified URL.
  
- ***Other HTTP Operations:***
    - **HEAD Method:**
        > The HEAD method asks for a response identical to that of a GET request, but without the response body.
    - **OPTIONS Method:**
        > The OPTIONS method is used to describe the communication options for the target resource.
    - **TRACE Method:**
        > The TRACE method performs a message loop-back test along the path to the target resource.
    - **CONNECT Method:**
        > The CONNECT method establishes a tunnel to the server identified by the target resource.
      
###### Note:
- All these methods are just nomenclature and can be used for any purpose. The server can interpret these methods in any way it wants.
  > - For example, a server can use the POST method to return a resource, or use the GET method to delete a resource.
  > - It all depends on how the server code is implemented.
  > - For example,
  > - ```
  >   @DeleteMapping(/products/{id})
  >   public void deleteProduct(@PathVariable("id") int id) {
  >       // create a new product with the given id
  >   }
  >   ```
  >   - In this example, the DELETE method is used to create a new product with the given id.
  >   - The DELETE method (@DeleteMapping) will call the deleteProduct method based on the id provided in the URL(/products/{id}) and create a new product with the given id.
  > - This is not a good practice, but it is possible.

#### Differences between POST, PUT, and PATCH:
The differences between POST, PUT, and PATCH can be confusing:
- A POST request creates a resource. The server assigns a URL for the new resource, and returns that URL to the client. 
    >  - In the REST model, you frequently apply POST requests to collections. 
    >  - The new resource is added to the collection. 
    >  - A POST request can also be used to submit data for processing to an existing resource, without any new resource being created.

- A PATCH request performs a partial update to an existing resource. The client specifies the URL for the resource.
  >  - The request body specifies a set of changes to apply to the resource.
  >  - This can be more efficient than using PUT, because the client only sends the changes, not the entire representation of the resource.
  >  - Technically PATCH can also create a new resource (by specifying a set of updates to a "null" resource), if the server supports this.

- A PUT request creates a resource or updates an existing resource. The client specifies the URL for the resource. 
    >  - The request body contains a complete representation of the resource. 
    >  - If a resource with this URL already exists, it is replaced. Otherwise, a new resource is created, if the server supports doing so.
    >  - PUT requests are most frequently applied to resources that are individual items, such as a specific customer, rather than collections. A server might support updates but not creation via PUT. Whether to support creation via PUT depends on whether the client can meaningfully assign a URL to a resource before it exists. 
    >  - If not, then use POST to create resources and PUT or PATCH to update.

In summary:
- POST is used to create a resource or submit data for processing.
- PATCH is used to perform a partial update (modify) to an existing resource.
- PUT is used to completely update (override) an existing resource. 

#### Idempotency:
- PUT requests must be idempotent. 
>   - If a client submits the same PUT request multiple times, the results should always be the same (the same resource will be modified with the same values).
>   - POST and PATCH requests are not guaranteed to be idempotent.
