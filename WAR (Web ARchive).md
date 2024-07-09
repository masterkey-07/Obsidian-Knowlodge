**Purpose:**

- **Web Applications:** WAR files are used to package Java web applications that run on a web server, such as Apache Tomcat, JBoss, or Jetty.

**Structure:**

- **WEB-INF Directory:** Contains web application-specific resources.
    - **web.xml:** Deployment descriptor (optional in modern Spring Boot applications).
    - **Classes:** Compiled Java classes placed under `WEB-INF/classes`.
    - **Libraries:** JAR files placed under `WEB-INF/lib`.
    - **Other Config Files:** Spring, Hibernate, or other framework configuration files.
- **Static Content:** HTML, JSP, CSS, JavaScript, and other static resources placed directly in the root or subdirectories.

**Common Usage:**

- **Servlet-Based Applications:** Packaging Java web applications that use servlets, JSPs, and other web technologies.
- **Spring MVC Applications:** Deploying Spring MVC or Spring Boot applications (although Spring Boot can also create executable JARs).

**Example Command:**

- To create a WAR file:
    
    bash
    
    Copiar código
    
    `jar cvf myapp.war -C webapp .`