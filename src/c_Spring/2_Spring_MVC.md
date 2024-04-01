## Spring MVC
Spring MVC is a part of the Spring Framework that is used to build web applications. It is based on the Model-View-Controller design pattern. It is a robust, flexible, and highly configurable framework that is used to develop web applications.

- M - Model: Represents the data of the application.
- V - View: Represents the UI of the application.
- C - Controller: Acts as an interface between Model and View.

## Journey of a request in Spring MVC
1. **User sends a request:** The user sends a request to the server.
2. **DispatcherServlet receives the request:** The DispatcherServlet receives the request.
3. **HandlerMapping maps the request to the appropriate controller:** The HandlerMapping maps the request to the appropriate controller.
4. **Controller processes the request:** The Controller Layer parses the request parameters and calls the appropriate service methods.
5. **Service Layer processes the request:** The Service Layer processes the request.
   >- The Service Layer contains the business logic of the application.
   >- All the algorithms and calculations are done in the Service Layer.

   - **Service Layer interacts with the Repository Layer:** The Service Layer interacts with the Repository Layer to fetch the data from the database.
     - The Service Layer might need to interact with databases, files, or other services.
     - Instead of directly interacting with the database, the Service Layer interacts with the Repository Layer.
       > - This is done to separate the business logic from the data access logic.
       > - Instead of creating an object of database directly in the Service Layer, i.e., a direct dependency between the Service Layer and the database, we create an object of Repository Layer and inject it into the Service Layer.
       > - This is done to make the application loosely coupled and easy to maintain, so that in the future, if we want to update the database, or migrate from MySql to any other for example, we can do it easily.
6. **Repository Layer fetches the data from the database:** The Repository Layer fetches the data from the database.

