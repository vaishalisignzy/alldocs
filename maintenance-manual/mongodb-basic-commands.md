# MongoDB basic commands

### **1. Log Into MongoDB**

The following command can be used to log into the MongoDB database. Make sure that the user with credentials such as _username_ and _password_ exist in the database mentioned in place of `dbname`.

```
mongo -u <username> -p <password> --authenticationDatabase <dbname> --host <host:port>
```

### **2. Show All Databases**

Run the following command to show the databases that are allocated to the above user.

```
show dbs
```

### **3. Select Database to Work With**

To start working with a particular database, the following command can be executed. Following two databases are available.

1. indusInd
2. indusIndFinnacle

```
use <databaseName>
```

### **4. Authenticate and Log Out From Database**

When switching to a different database using the `use dbName` command, the user is required to authenticate using a valid database user for that database. The following command can be used for authentication:

```
// Authenticate
db.auth("username", "password");
```

```
// Logout
db.logout()
```

### **5. List Down Collections, Users, Roles, etc.**

The following commands can be used to check existing collections, users, etc.

```
// List down collections of the current database
show collections;
// or
db.getCollectionNames();
```

```
// List down all the users of current database (Rarely used)
show users;
// or
db.getUsers();
```

```
// List down all the roles (Rarely used)
show roles
```

### **7. Insert a Document in a Collection**

Once a collection is created, the next step is to insert one or more documents. Following is a sample command for inserting a document in a collection.

```
// Insert single document
db.<collectionName>.insert({field1: "value", field2: "value"})
```

```
// Insert multiple documents
db.<collectionName>.insert([{field1: "value1"}, {field1: "value2"}])
db.<collectionName>.insertMany([{field1: "value1"}, {field1: "value2"}])
```

### **8. Save or Update Document**

The `save` command can be used to either update an existing document or insert a new one depending on the document parameter passed to it. If the `_id` passed matches an existing document, the document is updated. Otherwise, a new document is created. Internally, the`save` method uses either the `insert` or the `update` command.

```
// Matching document will be updated; In case, no document matching the ID is found, a new document is created
db.<collectionName>.save({"_id": new ObjectId("jhgsdjhgdsf"), field1: "value", field2: "value"});
```

### **9. Display Collection Records**

The following commands can be used to retrieve collection records:

```
// Retrieve all records
db.<collectionName>.find();
```

```
// Retrieve limited number of records; Following command will print 10 results;
db.<collectionName>.find().limit(10);
```

```
// Retrieve records by id
db.<collectionName>.find({"_id": ObjectId("someid")});
```

```
// Retrieve values of specific collection attributes by passing an object having 
// attribute names assigned to 1 or 0 based on whether that attribute value needs 
// to be included in the output or not, respectively.
db.<collectionName>.find({"_id": ObjectId("someid")}, {field1: 1, field2: 1});
db.<collectionName>.find({"_id": ObjectId("someid")}, {field1: 0}); // Exclude field1
```

```
// Collection count
db.<collectionName>.count();
```

### **10. Administrative Commands**

Following are some of the administrative commands that can be helpful in finding collection details such as storage size, total size, and overall statistics.

```
// Get the collection statistics 
db.<collectionName>.stats()
db.printCollectionStats()
```

```
// Latency statistics for read, writes operations including average time taken for reads, writes
// and related umber of operations performed
db.<collectionName>.latencyStats()
```

```
// Get collection size for data and indexes
db.<collectionName>.dataSize() // Size of the collection
db.<collectionName>.storageSize() // Total size of document stored in the collection
db.<collectionName>.totalSize() // Total size in bytes for both collection data and indexes
db.<collectionName>.totalIndexSize() // Total size of all indexes in the collection
```

