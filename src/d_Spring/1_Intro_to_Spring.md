# Spring Framework
Spring is an open-source lightweight framework that is used to develop loosely-coupled enterprise level Java applications.

Spring has a core framework that provides essential core set of functionalities + additional modules that provide additional functionality based on the application requirements.(Web, Data, Cloud, Authentication, etc.)

## Spring Core Framework:
1. ### Dependency Injection:
    - Spring injects the dependencies of an object at runtime. 
    - This is done by defining the dependencies in a configuration file, making the application loosely coupled and easy to maintain. So, testing and future modifications are easy.
    - It is better to add dependencies outside the class rather than inside the class, so that the class is not tightly coupled and the dependencies can be reused, modified, or replaced easily, making them loosely coupled. 
    - Spring provides 2 types of DI:
        - Constructor Injection
        - Setter/Method Injection
    - Spring provides a very easy way to inject the dependencies using annotations.

   #### Dependency Injection vs Dependency Inversion:
     - Dependency Injection is a design pattern that is used to remove the hard-coded dependencies and make the application loosely coupled and easy to maintain.
       > - Dependency Injection says that whenever a class is dependent on another class, where will that dependency be created?
       > - The class should not create the dependency itself. Rather, the dependency should be injected from outside, so that the class is not tightly coupled.
     - Dependency Inversion is a principle that says that the high-level modules should not depend on low-level modules, but they should depend on abstractions. And the abstractions should not depend on details, but the details should depend on abstractions.
       > - One class should not depend on another class, but on an interface.
       > - The details of the class should depend on the interface, not the other way around.
     - None of the two are a way to implement the other. They are two different concepts, talking about similar things.
  
   - To conclude:
     - Dependency Inversion is a design principle that says "Instead of 2 concrete classes directly dependent on each other, they should depend on each other via an interface."
     - Dependency Injection says "Instead of creating an object of the dependency inside the class, we pass/inject the object of that dependency from outside the class via a constructor or a setter method."

2. ### Inversion of Control:
    - Whenever we create an application, there are multiple common dependencies which have to be injected in multiple classes.
    - In traditional programming, these are created by the programmer.
    - Whenever a framework does DI for us, it is called Inversion of Control.
    - Spring provides a very easy way to inject the dependencies using beans.
    
    #### Spring Bean:
    - A bean is an object that Spring will automatically create as well as inject the dependencies for you whenever and wherever needed and manage the lifecycle of the object. 
    - A Spring Bean is an object that is instantiated, assembled, and managed by the Spring IoC container.
    - Think of a bean as a special object that you give to Spring, so that it can inject the dependencies for you automatically whenever needed and manage the lifecycle of the object.
    - When we start a Spring application, Spring creates objects of all beans and puts them in the Spring container.

> ### To summarize, Spring is a lightweight framework that works on the principle of Dependency Injection, which allows us to create beans that are automatically created as well as injected into other objects.

## Spring Boot:
- Spring Boot is a Spring project that simplifies the Spring configuration and setup other projects.
- Spring Boot is a project that is built on top of the Spring Framework. It provides a simpler and faster way to set up, configure, and run both simple and web-based applications.
- It eliminates the need to write any configuration files, annotations, or boilerplate code.
- It also automatically configures a project with all the known best practices and a set of defaults.

Any good framework should have the following features:
1. **An Opinionated Default Configuration:** It should have a set of best-practices/defaults that are known to work well together.
2. **Modifiable Defaults:** It should allow you to modify the defaults as per your requirements as easily as possible.