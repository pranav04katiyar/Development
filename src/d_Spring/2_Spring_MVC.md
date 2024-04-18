## MVC
**MVC is a design pattern wrt how the APIs should be structured.**
- It says that the code of the application should be divided into different classes, each with a specific work.
> - It has 3 parts:
>    - ***Model:*** Represents the data of the application that are stored in the Database.
>    - ***View:*** Represents the UI of the application. Earlier, and even today in some cases, the backend used to generate the UI code as well. But now, the backend only sends the data to the frontend, and the frontend generates the UI code.
>    - ***Controller:*** These are the classes that receive the request. Acts as an interface between Model and View.
- MVC can be implemented in any language, not just Java.
- MVC can be compared to being SRP for APIs.

### MVC vs REST
- MVC is a design pattern, while REST is an architectural style.
- MVC helps in defining how the code should be structured.
- REST helps in defining how the APIs should be named and how they should be accessed.

## Various Layers in MVC
1. **Controller processes the request:** The Controller Layer parses the request parameters and calls the appropriate service methods.
2. **Service Layer processes the request:** The Service Layer processes the request.
   >- The Service Layer contains the business logic of the application.
   >- All the algorithms and calculations are done in the Service Layer.
   - **Service Layer interacts with the Repository Layer:** The Service Layer interacts with the Repository Layer to fetch the data from the database.
     - The Service Layer might need to interact with databases, files, or other services.
     - Instead of directly interacting with the database, the Service Layer interacts with the Repository Layer.
       > - This is done to separate the business logic from the data access logic.
       > - Instead of creating an object of database directly in the Service Layer, i.e., a direct dependency between the Service Layer and the database, we create an object of Repository Layer and inject it into the Service Layer.
       > - This is done to make the application loosely coupled and easy to maintain, so that in the future, if we want to update the database, or migrate from MySql to any other for example, we can do it easily.
3. **Repository Layer fetches the data from the database:** The Repository Layer fetches the data from the database.
4. **Database sends the data to the Repository Layer:** The database sends the data to the Repository Layer.
     > - Database contains the data of the application.
     > - Information about different entities is stored in the database.
     - **These are called Models in the MVC architecture.**

## Spring MVC
Spring MVC is a part of the Spring Framework that is used to build web applications. It is based on the Model-View-Controller design pattern. It is a robust, flexible, and highly configurable framework that is used to develop web applications.

### Journey of a request in Spring Boot
1. **User sends a request:** 
   > - The user sends a request to the server.
2. **Dispatcher Servlet receives the request:** 
   > - The Dispatcher Servlet receives the request.
   > - The Dispatcher Servlet is the front controller of the Spring MVC.
   > - It receives all the requests and then dispatches them to the appropriate controller.
3. **Dispatcher Servlet asks HandlerMapping for the correct method to serve the API:** 
   > - The Dispatcher Servlet asks the HandlerMapping to map the request to the correct method in the Controller.
   > - HandlerMapping will map the request to the correct method in the Controller:** The HandlerMapping maps the request to the correct method in the Controller and returns the method to the Dispatcher Servlet.
4. **Dispatcher Servlet calls the mapped Controller:** 
   > - The Dispatcher Servlet calls the Controller based on the method returned by the HandlerMapping.
5. **Controller processes the request:**
   > - The Controller processes the request, work on the request parameters using the appropriate Service Layer, Repository Layer, and Model and returns the response to the Dispatcher Servlet.
6. **Dispatcher Servlet sends the response to the user:**
   > - The Dispatcher Servlet sends the response to the user.