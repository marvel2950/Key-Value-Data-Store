<h1>Key-Value-Data-Store</h1>
<h3>Freshworks Assignment</h3>
<h3>A file-based key-value data store that supports the basic CRD (create, read, and delete) operations.
</h3>
<br>
<h2>Environment Setup</h2>
<h3>
1. Clone the repository using the command -> git clone https://github.com/whoakarsh/Key-Value-Data-Store.git <br>
2. Install Python3.6 or higher <br>
3. Run __init__.py to run the backend server.
</h3>
<br>
<h2>Accessing DataStore CRD operations as a library</h2>
<h3>
1. A class named DataStore in the file __init__.py contains all the CRD operations.<br>
2. A class function DataStore(file_path).create(key,value, time_to_live) can be used to create a data in DataStore.<br>
3. A class function DataStore(file_path).read(key) can be used to read a data from the DataStore.<br>
4. A class function DataStore(file_path).delete(key) can be used to delete a data from the DataStore.<br>
</h3>
<br>
<h2>Functional requirements</h2>
<h3>
1. It can be initialized using an optional file path. If one is not provided, it will reliably create itself in a reasonable location on the laptop.<br>
2. A new key-value pair can be added to the data store using the Create operation. The key is always a string capped at 32chars. The value is always a JSON obiect capped at 16KB.<br>
3. If Create is invoked for an existing key, an appropriate crror must be returned.<br>
4. A Read operation on a key can be performed by providing the key, and receiving the value in response, as a JSON object.<br>
5. A Delete operntion can be performed by providing the key.<br>
6. Every key supports setting a Time-To-Live property when it is created. This property is optional. If provided, it will be evaluated as an integer defining the number of seconds the key must be retained in the data store. Once the Time-TO-Live for a key has expired, the key will no longer be available for Read or Delete operations.<br>
7. Appropriate error responses must always be returned to client if it uses the data store in unexpected ways or breaches any limits.
</h3>
<br>
<h2>Non-functional requirements</h2>
<h3>
1. The size of the file storing data must never exceed 1GB.<br>
2. More than one client process cannot be allowed to use the same file as a data store at any given time.<br>
3. A client process is allowed to access the data store using multiple threads, if it desires to the data store must therefore be thread-safe <br>
4. The client will bear as little memory costs as possible to use this data store, while deriving maximum performance with respect to response times for accessing the data store.
</h3>