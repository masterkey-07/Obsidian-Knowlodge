DIfferences between [[JAR (Java ARchive)|JAR]] and [[WAR (Web ARchive)|WAR]]

### Key Differences

1. **Use Case:**
    - **JAR:** For general Java applications, libraries, and utilities.
    - **WAR:** Specifically for web applications that run on a web server.
2. **Content:**
    - **JAR:** Contains compiled Java classes and resources, typically without web-specific configuration.
    - **WAR:** Includes web application directories (`WEB-INF`), web.xml, classes, and libraries required for web deployment.
3. **Deployment:**
    - **JAR:** Executed using the `java -jar myapp.jar` command or used as a library dependency in other projects.
    - **WAR:** Deployed to a web server, which handles the web application lifecycle.
4. **Structure:**
    - **JAR:** Flat structure with optional manifest file.
    - **WAR:** Hierarchical structure with `WEB-INF` directory for web application configuration and libraries.

### When to Use Which

- **Use JAR:**
    
    - For standalone Java applications that don’t require a web server.
    - For libraries that will be used as dependencies in other projects.
    - For Spring Boot applications that are packaged as executable JARs (preferred in microservices architecture).
- **Use WAR:**
    
    - For traditional Java EE web applications.
    - For applications that require deployment on a servlet container or application server.
    - For large enterprise applications that benefit from the separation of web and business logic.

### Conclusion

Understanding the difference between JAR and WAR files is crucial for packaging and deploying Java applications appropriately. Use JAR for general applications and libraries, and WAR for web applications that need to run on a web server. Each packaging method serves a specific purpose and follows distinct conventions, making it essential to choose the right one based on your project's requirements.