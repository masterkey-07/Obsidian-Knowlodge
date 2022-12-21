#database

### Uses [[R Tree]] 


## Connection Limit

### [[SQLite]] does not have a connection limit, but it locks the read/write of the database when another process is reading/writing it.

### So, applications that need multiple connections working concurrently, it is better to use another database.
