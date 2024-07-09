**Purpose:**

- **General Java Applications:** JAR files are used to package standalone Java applications or libraries that can be distributed and executed on any Java-enabled environment.

**Structure:**

- **Manifest File:** Contains metadata about the JAR, such as the main class to execute.
- **Class Files:** Compiled Java classes.
- **Resources:** Additional files like properties, XML, and images.
- **Libraries:** Other JARs that your application depends on.

**Common Usage:**

- **Libraries and Utilities:** Packaging reusable Java libraries or utility classes.
- **Standalone Applications:** Distributing Java applications that can be executed directly (with a `Main-Class` specified in the manifest).

**Example Command:**

- To create a JAR file:
    
    bash
    
    Copiar código
    
    `jar cvf myapp.jar -C bin .`
    