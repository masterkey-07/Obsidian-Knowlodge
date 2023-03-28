 #note 
[[Web Development]] Concept

![[Web Application Archtecture 2022-12-13 07.41.53.excalidraw|3000]]

# Client 

### User Interface, to make requests to the server.

# Load Balancer

### Manage the multiple requests throught the multiple services.

# Services

### Application to handle logic, process requests.

# Connection Pool

### Handle the limit of connections to the Database.

# Databases

### WriteOnly : Perform only Write Actions

### ReadOnly : Perform only Read Actions

### This division is for allow better performance.

# Cache Database

### Hold data that is common, to prevent a lot of unnecessary processing.

### Fast Access Data, because it is in Memory.

# Workers

### Handle Requests Later, consume or produce data.