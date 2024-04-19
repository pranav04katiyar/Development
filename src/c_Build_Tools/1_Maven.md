# What is a build tool?
- A build tool is a tool that automates the process of building a project.
- It automates the process of compiling source code into binary code, packaging binary code, and deploying the packaged code to a server.
- It also automates the process of downloading third party libraries and including them in the project.
- Examples of build tools include Maven, Gradle, Ant, etc.

# What is Maven?
- Maven is a build tool that makes it easy to download third party libraries and include them in projects using Java and other JVM languages like Groovy, Kotlin, Scala, etc. 
- It also makes it easy to build and package your project. 
- Maven addresses two aspects of building software:
  - > It describes how software is built.
  - > It describes its dependencies.

# POM: Project Object Model
  - pom.xml: This is the file where you define your project's configuration.
  - It is specific to Maven and is used to define the project's configuration.
## Maven POM Basics:
1. Group ID: This is a unique identifier for the project.
   - > It is usually the reverse of the domain name of the organization that owns the project.
2. Artifact ID: This is a unique identifier for the project's artifact. It is the project ID which is the name of the project.
   - > The Group ID and Artifact ID together uniquely identify a project.
3. Version: This is the version of the project.
   - > It is used to identify different versions of the project.
     >  - SNAPSHOT: This is used to identify a project that is under development.
     >  - RELEASE: This is used to identify a project that is ready for release.
     >  - LATEST: This is used to identify the latest version of the project.
- Example of defining the project's configuration in the POM file:
  ```xml
  <project>
    <modelVersion>4.0.0</modelVersion>
    <groupId>com.example</groupId>
    <artifactId>my-project</artifactId>
    <version>1.0.0</version>
  </project>
  ```
  - In this example, the project tag is used to define the project's configuration.
    - The modelVersion tag is used to define the version of the POM file.
    - The groupId tag is used to define the group ID of the project.
    - The artifactId tag is used to define the artifact ID of the project.
    - The version tag is used to define the version of the project.

## Maven POM Properties:
- Properties are used to define variables that can be used in the POM file.
- Properties like compiler source, compiler target tell Maven which version of Java to use to compile the project (e.g. 11, 17, 21 etc.).
- There are many other properties that can be defined in the POM file, like junit version, according to the project's requirements.
- Example of defining properties in the POM file:
  ```xml
  <properties>
    <maven.compiler.source>11</maven.compiler.source>
    <maven.compiler.target>11</maven.compiler.target>
  </properties>
  ```
  - In this example, the properties tag is used to define the properties of the project.
    - The maven.compiler.source property is used to define the source version of Java to use to compile the project.
    - The maven.compiler.target property is used to define the target version of Java to use to compile the project.

## Maven POM Build:
- The build section of the POM file is used to define the project's build configuration.
- It is used to define the plugins that are used to build the project.
- The plugins can be used to test the project, compile the project, deploy the project, etc.
- Example of defining the build section in the POM file:
  ```xml
  <build>
    <plugins>
      <plugin>
        <groupId>org.apache.maven.plugins</groupId>
        <artifactId>maven-compiler-plugin</artifactId>
        <version>3.8.1</version>
        <configuration>
          <source>11</source>
          <target>11</target>
        </configuration>
      </plugin>
    </plugins>
  </build>
  ```
  - In this example, the build section is used to define the maven-compiler-plugin.
    - The plugin tag is used to define the plugin that is used to build the project. 
    - The maven-compiler-plugin is used to compile the project.
      - The groupId of the maven-compiler-plugin is set to `org.apache.maven.plugins`
      - The artifactId of the maven-compiler-plugin is set to `maven-compiler-plugin`
      - The version of the maven-compiler-plugin is set to `3.8.1`
      - The configuration tag is used to define the configuration of the maven-compiler-plugin.
        - The source tag is used to define the source version of Java to use to compile the project.
        - The target tag is used to define the target version of Java to use to compile the project.

## Maven POM Dependencies:
- There can be instances when you need to use third party libraries in your project to add functionality. That's where dependencies come in.
- Dependencies are used to define the third party libraries that are used in the project.
  - Maven downloads these libraries from the Maven Central Repository and includes them in the project.
- A project can have multiple dependencies.
- It's not necessary to hardcode the version of the dependency in the POM file.
  - Maven can also work with the version mentioned in the properties section of the POM file if the dependency is of the same plugin.
  - This allows us to reuse the version of the dependency in multiple places in the POM file. 
- Dependencies can also have scopes like compile, test, runtime, etc.
  - The scope of the dependency defines when the dependency is needed in the project.
  - For example, a dependency with a scope of compile is needed when the project is compiled.
  - A dependency with a scope of test is needed when the project is tested.
  - If the scope is not mentioned, the default scope is compile.
- To add a dependency to the project, you need to add the dependency tag to the dependencies section of the POM file.
  - The dependency tag has three tags: groupId, artifactId, and version. Scope is optional.
  - The groupId and artifactId together uniquely identify the dependency.
  - The version tag is used to specify the version of the dependency.
- To find the dependency that you need to add to the project, you can search for it on the Maven Central Repository website.
  - The Maven Central Repository is a repository that contains all the third party libraries that can be used in a Maven project.
  - You can search for the dependency that you need on the Maven Central Repository website and find the groupId, artifactId, and version of the dependency.
  - The URL of the Maven Central Repository is `https://search.maven.org/`
- Example of adding a dependency to the project:
  ```xml
  <dependencies>
    <dependency>
      <groupId>org.apache.commons</groupId>
      <artifactId>commons-lang3</artifactId>
      <version>3.12.0</version>
    </dependency>
  </dependencies>
  ```
- To see whether the dependency has been added to the project in the IDE, you can run the following command:
  ```shell
    mvn dependency:tree
    ```
  - This command will show you the dependencies that have been added to the project.
  - We can also see the dependencies that have been added to the project in the IDE by expanding the Maven Dependencies section in the External Libraries section of the project in the IDE.
