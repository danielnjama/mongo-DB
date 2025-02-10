# MongoDB Course Outline

## Course Overview
Welcome to the MongoDB course! This course is designed to provide a comprehensive understanding of MongoDB, covering everything from the basics of NoSQL databases to advanced MongoDB features and techniques for building and managing scalable databases. By the end of this course, you'll be equipped with the skills needed to build, optimize, and manage MongoDB databases in a real-world setting.

---

## Course Outline

### 1. Introduction to NoSQL Databases
- **Overview of NoSQL vs. SQL Databases**
- **Types of NoSQL Databases**
  - Key-Value Stores
  - Document Stores
  - Column-Family Stores
  - Graph Databases
- **Advantages of NoSQL and Use Cases**

### 2. Introduction to MongoDB
- **What is MongoDB?**
  - Document-Oriented Model
  - JSON and BSON
- **Setting Up MongoDB**
  - Installation Guide
  - MongoDB Atlas Overview (Cloud Setup)
- **Basic MongoDB Commands**

### 3. Core MongoDB Concepts
- **Collections and Documents**
  - Structure of a Document
  - Creating Collections and Documents
- **CRUD Operations**
  - Create, Read, Update, and Delete Operations
- **Schema Design and Data Modeling**
  - Embedding vs. Referencing
  - Denormalization and One-to-Many, Many-to-Many Relationships

### 4. Querying and Aggregation
- **Querying in MongoDB**
  - Query Selectors and Projection
  - Advanced Query Operators
- **Indexing**
  - Purpose of Indexing in MongoDB
  - Types of Indexes (Single Field, Compound, Text, Geospatial)
  - Indexing Best Practices
- **Aggregation Framework**
  - Introduction to Aggregations and Pipelines
  - Common Aggregation Stages (Match, Group, Project)
  - Building Complex Aggregations

### 5. Security and Best Practices
- **Authentication and Authorization**
  - Role-Based Access Control (RBAC)
  - Configuring User Roles
- **Data Encryption**
  - In-Transit and At-Rest Encryption
  - Key Management
- **Backup and Recovery**
  - Backup Strategies
  - Restoring Databases

### 6. MongoDB Administration
- **MongoDB CLI Tools**
  - Overview of MongoDB Shell (mongosh)
  - Monitoring and Management Tools
- **Monitoring MongoDB Performance**
  - Using MongoDB Atlas Monitoring
  - Common Metrics to Track
- **Automation and Scheduling**
  - Automating Backups, Monitoring, and Alerts
  - Scheduling Maintenance Tasks


---

## Prerequisites
- Basic knowledge of databases and SQL

## Course Objectives
By the end of this course, students will:
1. Understand the fundamentals of MongoDB and NoSQL databases.
2. Be able to design, query, and optimize MongoDB databases.
3. Have the skills to configure MongoDB in various environments.
4. Understand MongoDB’s advanced features for scalability and performance.
5. Be equipped with best practices for MongoDB administration and security.

---

## Additional Resources
- [MongoDB Documentation](https://docs.mongodb.com/)
- [MongoDB University](https://university.mongodb.com/)
- [MongoDB Community Forums](https://www.mongodb.com/community/forums/)

---


---
# 1. Introduction to NoSQL Databases

## Overview of NoSQL vs. SQL Databases

### What is NoSQL?
NoSQL databases are a category of database management systems designed to store and retrieve large volumes of unstructured, semi-structured, or structured data. Unlike traditional relational databases (SQL databases), which store data in tables and use SQL for data manipulation, NoSQL databases provide more flexible data models that scale horizontally.

### Key Differences: SQL vs. NoSQL
| Feature               | SQL Databases                    | NoSQL Databases                  |
|-----------------------|----------------------------------|----------------------------------|
| **Data Structure**    | Tables with rows and columns     | Flexible models (document, key-value, etc.) |
| **Schema**            | Fixed schema                     | Schema-less or dynamic schema    |
| **Scaling**           | Vertical (adding resources to a single server) | Horizontal (adding more servers) |
| **ACID Compliance**   | ACID-compliant                   | Generally not ACID-compliant (some exceptions) |
| **Joins**             | Supports joins                   | Usually does not support joins directly |
| **Query Language**    | SQL                              | Varies (JSON, Query DSL, APIs)   |

SQL databases are best suited for applications that require structured data, strict consistency, and complex querying. NoSQL databases excel with large volumes of diverse, rapidly changing data.

## Types of NoSQL Databases

1. **Key-Value Stores**
   - Stores data as key-value pairs, similar to a dictionary or hash map.
   - Data retrieval is done by referencing the key.
   - **Use Cases**: Caching, session storage.
   - **Examples**: Redis, DynamoDB, Riak.

2. **Document Stores**
   - Stores data in a document format, typically JSON or BSON.
   - Allows nested data structures, making it easy to store complex data.
   - **Use Cases**: Content management, e-commerce catalogs.
   - **Examples**: MongoDB, Couchbase, DocumentDB.

3. **Column-Family Stores**
   - Organizes data into columns and column families, allowing efficient storage of sparse data.
   - Optimized for read-heavy workloads and big data.
   - **Use Cases**: Data warehousing, real-time analytics.
   - **Examples**: Cassandra, HBase.

4. **Graph Databases**
   - Stores data in nodes and edges to represent relationships between data.
   - Ideal for applications with complex relationships.
   - **Use Cases**: Social networks, fraud detection, recommendation engines.
   - **Examples**: Neo4j, ArangoDB, Amazon Neptune.


# MongoDB Terminologies

This document provides definitions of popular MongoDB terminologies to help understand key concepts used in MongoDB databases. 

## Key MongoDB Terminologies

### General Terms

- **Database**: A container for collections in MongoDB. Each MongoDB deployment can host multiple databases, each storing related collections.

- **Collection**: A grouping of documents within a database, similar to a table in relational databases. Collections hold documents in a JSON-like format and have a flexible schema, meaning documents can vary in structure.

- **Document**: The fundamental data unit in MongoDB, stored as a BSON (Binary JSON) object. Documents are similar to rows in relational databases but can contain nested fields and arrays, offering a more dynamic structure.

- **Field**: A key-value pair in a document, similar to a column in a relational database. Fields in MongoDB are flexible and do not have to be consistent across all documents in a collection.

---

### Data Model Terms

- **Schema-less**: MongoDB is schema-less, meaning documents in a collection do not need to follow a fixed schema. Fields can vary between documents, offering flexibility for different data types and structures.

- **BSON (Binary JSON)**: The format MongoDB uses to store documents. BSON is similar to JSON but optimized for data storage and transfer, supporting additional data types like dates and binary data.

- **Embedded Document**: A document stored within another document. Embedded documents allow for hierarchical data storage, which can improve read performance and make data models more intuitive.

- **Array**: A data type in MongoDB that stores multiple values in a single field, such as a list of items. Arrays allow documents to store more complex and related data within a single record.

---

### Indexing and Query Terms

- **Index**: A data structure that improves query performance by allowing MongoDB to quickly locate documents within a collection. Indexes can be created on one or more fields in a document.

- **Compound Index**: An index on multiple fields in a collection, used to support queries that filter or sort by multiple fields.

- **Aggregation**: A MongoDB feature used to process data and return computed results. Aggregation operations include filtering, grouping, and calculating values, similar to SQL aggregation functions.

- **Pipeline**: A series of aggregation stages in MongoDB. Each stage performs an operation on the data, passing the results to the next stage.

---

### Data Management Terms

- **Replication**: The process of synchronizing data across multiple servers to ensure data redundancy and availability. MongoDB uses **Replica Sets** for replication.

- **Replica Set**: A group of MongoDB servers that maintain the same data. A replica set has a primary node (handles write operations) and secondary nodes (replicate data from the primary), ensuring data availability and redundancy.

- **Sharding**: A method for distributing data across multiple servers (or shards) to scale horizontally. MongoDB uses a **Shard Key** to divide data among shards.

- **Shard Key**: A field or set of fields used to determine how data is distributed across shards in a sharded MongoDB cluster.

---

### Security Terms

- **Authentication**: The process of verifying the identity of users attempting to access MongoDB. MongoDB supports various authentication mechanisms, including username and password.

- **Authorization**: The process of defining which actions a user can perform in MongoDB after they are authenticated. MongoDB uses Role-Based Access Control (RBAC) for authorization.

- **Role-Based Access Control (RBAC)**: A security model in MongoDB where users are assigned roles, and each role grants specific permissions on databases and collections.

---

### Performance and Maintenance Terms

- **Profiler**: A MongoDB tool for analyzing database operations, such as queries and writes, to identify and optimize slow operations.

- **Cursor**: An object used to iterate over the results of a query. Cursors allow MongoDB to handle large datasets by returning results in batches.

- **Log Rotation**: The process of archiving old MongoDB logs and creating new logs to manage log size and improve performance.

- **Snapshot**: A backup technique that captures the state of the database at a specific point in time, often used for backups in production environments.

---

### Advanced Terms

- **MongoDB Atlas**: A cloud-based, fully managed MongoDB service that offers automated backups, monitoring, scaling, and security features.

- **mongod**: The primary daemon process for MongoDB, responsible for managing data storage, accepting connections, and performing operations.

- **mongos**: A routing service used in sharded MongoDB clusters to route queries to the appropriate shard based on the shard key.

- **WiredTiger**: The default storage engine for MongoDB since version 3.2. WiredTiger offers efficient storage management and supports features like compression and concurrency control.

This list covers the essential MongoDB terminology, providing a foundation for understanding MongoDB databases and their management.



## Advantages of NoSQL Databases

- **Scalability**: Most NoSQL databases support horizontal scaling, allowing data to be distributed across multiple servers.
- **Flexibility**: NoSQL databases offer dynamic schemas, making it easier to adapt to changing data requirements.
- **Performance**: By focusing on specific data access patterns, NoSQL databases can be optimized for high-speed reads and writes.
- **Cost-Effectiveness**: Horizontal scaling with commodity hardware can reduce infrastructure costs.

## NoSQL Database Use Cases

### When to Use NoSQL
- **Rapidly Growing Data**: Applications that generate large amounts of data (e.g., IoT, social media).
- **Frequent Schema Changes**: Scenarios where data structures are evolving or unstructured.
- **High-Speed Data Processing**: Applications that require fast, scalable performance.
- **Distributed Data Storage**: Use cases where data must be distributed across multiple data centers or regions.

### When Not to Use NoSQL
- **Complex Transactions**: Applications that require complex joins or multi-table transactions may benefit more from SQL databases.
- **Strong Consistency Needs**: For applications where strict consistency is critical (e.g., financial transactions), SQL databases or ACID-compliant NoSQL options are preferred.

---

By understanding these concepts, you’ll gain insight into where NoSQL databases, including MongoDB, can be most effectively applied and how they differ fundamentally from traditional relational databases.


# 2. Introduction to MongoDB

## What is MongoDB?

MongoDB is a popular, open-source NoSQL database known for its flexible document-oriented data model. Unlike traditional relational databases that store data in rows and columns, MongoDB stores data in JSON-like documents, making it easy to work with structured, semi-structured, and unstructured data.

### Key Features of MongoDB:
- **Document-Oriented**: Stores data in JSON-like BSON (Binary JSON) format, allowing for nested documents and arrays.
- **Schema Flexibility**: MongoDB allows a flexible schema design, enabling the addition of new fields without affecting existing records.
- **Horizontal Scalability**: MongoDB supports horizontal scaling through sharding, which distributes data across multiple servers.
- **High Availability**: Through replica sets, MongoDB provides redundancy and automated failover.
- **Powerful Query Language**: MongoDB offers a rich query language and aggregation framework for complex data retrieval and processing.

### JSON and BSON
- **JSON (JavaScript Object Notation)**: A lightweight, human-readable data format. MongoDB’s data model is similar to JSON, making it easy to interact with from modern applications.
- **BSON (Binary JSON)**: MongoDB’s storage format, a binary representation of JSON, optimized for performance with additional data types like Date, ObjectId, etc.

---

## Setting Up MongoDB

MongoDB can be set up in different environments, either locally or in the cloud.

### Installation Guide

#### Local Installation
1. **Download MongoDB**: Obtain the appropriate version of MongoDB for your operating system from the [official MongoDB website](https://www.mongodb.com/try/download/community).
2. **Install MongoDB**: Follow the installation steps based on your OS (Windows, macOS, or Linux).
3. **Start MongoDB Server**: Run the `mongod` command to start the MongoDB server on the default port (27017).
4. **Connect to MongoDB**: Use the MongoDB shell (mongosh) to interact with your MongoDB instance.

#### Cloud Setup: MongoDB Atlas
MongoDB Atlas is a fully managed cloud-based MongoDB service that simplifies setup and scaling. It provides automatic backups, security, and monitoring.

1. **Sign Up**: Create an account on [MongoDB Atlas](https://www.mongodb.com/cloud/atlas).
2. **Create a Cluster**: Select the region and configuration to set up a cluster.
3. **Connect to MongoDB Atlas**: Obtain the connection string and connect to your cluster using the MongoDB shell, Compass, or an application.

#### MongoDB on Docker container
Ensure Docker is installed on your machine. Create a mongodb docker container as below:
```bash
docker run -d  --name mongodb -p 27017:27017  -e MONGO_INITDB_ROOT_USERNAME=admin -e MONGO_INITDB_ROOT_PASSWORD=password mongo
```
Access mongoDB with the following:
Note: mongosh is available on MongoDB V5.0+. Earlier versions have mongo.
```
docker exec -it mongodb mongo -u admin -p password
OR
docker exec -it mongodb mongosh -u admin -p password
```

### MongoDB Tools
- **MongoDB Shell (mongosh)**: Command-line interface for MongoDB.
- **MongoDB Compass**: GUI-based tool for visual interaction with MongoDB data.
- **MongoDB Atlas**: Cloud-based platform for managing MongoDB clusters and databases.

---
## MongoDB Data Types
MongoDB supports a variety of data types that enable the storage of diverse data structures. Here are the primary data types used in MongoDB:

## Core Data Types

1. **String**: Used to store text data. In MongoDB, strings must be UTF-8 encoded.
```javascript
{ name: "Alice" }
```
2. **Integer**: Used to store whole numbers, such as counts, indexes, or any numeric value without a decimal.
```javascript
{ age: 30 }
```
3. **Double**: Used to store floating-point numbers with decimal points.
```javascript
{ price: 19.99 }
```
4. **Boolean**: Used to store binary values true or false.
```javascript
{ hasLaptop: true }
```
5. **Array**: Used to store a list of values, which can contain mixed data types, including other arrays and documents.
```javascript
{ tags: ["technology", "news", "coding"] }
```
6. **Date**: Used to store dates and times. Dates are stored with millisecond precision.
```javascript
{ createdAt: new Date() }
```
7. **Embedded Document (Object)**: A document within a document, allowing for nested structures and complex data models.
```javascript
{ address: { city: "New York", zip: "10001" } }
```
8. **Null**: Represents a null value, typically used to indicate missing or unknown data.
```javascript
{ middleName: null }
```

MongoDB's flexible data types enable dynamic and complex data structures within documents.

## Basic MongoDB Commands

Here are some essential MongoDB commands to get started:

### 1. Connecting to MongoDB
- **Start MongoDB**: Run `mongod` in your terminal to start the server.
- **Access MongoDB Shell**: Run `mongosh` to open the MongoDB shell.

### 2. Database Operations
- **Show Databases**: List all databases.
  ```shell
  show dbs

- Create/Use a Database: Switch to a database or create it if it doesn't exist
```
use myDatabase
```
### 3. Collection Operations
- Show Collections: List all collections in the current database
```
show collections of all items in a collection
```
db.myCollection.countDocuments({})
```
OR
```
db.myCollection.aggregate([
  { $count: "output-name" }
])

```
```
- Show a count of 
- Create a Collection: Collections are created implicitly when a document is added. Alternatively, create explicitly:
```
db.createCollection("myCollection")
```

### 4. CRUD Operations (Basics)
**Insert Documents**
- Insert a single document:
```
db.myCollection.insertOne({ name: "Alice", age: 25 })
```
- Insert multiple documents:
```
db.myCollection.insertMany([{ name: "Bob", age: 30 }, { name: "Charlie", age: 35 }])
```

**Read Documents**
- Find all documents in a collection
```
db.myCollection.find()
```
- Find documents with specific criteria
```
db.myCollection.find({ age: { $gt: 25 } })
```
**Update Documents**
- Update a single document:
```
db.myCollection.updateOne({ name: "Alice" }, { $set: { age: 26 } })
```
- Update multiple documents
```
db.myCollection.updateMany({ age: { $gt: 25 } }, { $set: { active: true } })
```
- Increase a record: Increase the age of all by 10
```
db.myCollection.updateMany({},{$inc: {age: 10}})
```
- Increase a record: Increase the age of user with given id
```
db.myCollection.updateMany({_id: 20},{$inc: {age: 5}})
```

**Delete Documents**
- Delete a single document:
```
db.myCollection.deleteOne({ name: "Alice" })
```
- Delete multiple documents
```
db.myCollection.deleteMany({ age: { $lt: 30 } })
```
# 3. Core MongoDB Concepts

## Collections and Documents

### Structure of a Document
In MongoDB, data is stored in **documents**. Each document is a JSON-like object (stored internally as BSON) with key-value pairs. Documents are schema-flexible, allowing different documents within the same collection to have different fields and structures.

Example of a MongoDB document:
```json
{
  "_id": "507f191e810c19729de860ea",
  "name": "John Doe",
  "age": 29,
  "email": "johndoe@example.com",
  "address": {
    "street": "123 Main St",
    "city": "New York",
    "zip": "10001"
  },
  "interests": ["reading", "traveling"]
}
```
**Creating Collections and Documents**
- Collections are like tables in a relational database. Collections contain documents and are created implicitly when you add a document to a non-existent collection.
- You can also create a collection explicitly:
```
db.createCollection("users")
```

**CRUD Operations**
>> MongoDB supports basic CRUD (Create, Read, Update, Delete) operations, which form the backbone of working with data in any application.

**Create Operations**
- Insert a Document: Inserts a single document into a collection
```
db.users.insertOne({ name: "Alice", age: 25 })
```
- Insert Multiple Documents: Inserts multiple documents at once
```
db.users.insertMany([{ name: "Bob", age: 30 }, { name: "Charlie", age: 35 }])
```
**Read Operations**
- Find All Documents: Retrieves all documents in a collection
```
db.users.find()
```
- Find with Filters: Retrieves documents based on conditions
```
db.users.find({ age: { $gte: 30 } })
```
- Projection: Limit the fields returned by a query
```
db.users.find({ age: { $gte: 30 } }, { name: 1, age: 1 })
```
**Update Operations**
- Update a Single Document: Updates one document based on criteria
```
db.users.updateOne({ name: "Alice" }, { $set: { age: 26 } })
```
- Update Multiple Documents: Updates multiple documents based on criteria
```
db.users.updateMany({ age: { $lt: 30 } }, { $set: { active: true } })
```
- Replace Document: Replaces the entire document
```
db.users.replaceOne({ name: "Alice" }, { name: "Alice", age: 27 })
```
**Delete Operations**
- Delete a Single Document: Deletes one document based on criteria
```
db.users.deleteOne({ name: "Alice" })
```
- Delete Multiple Documents: Deletes all documents matching criteria.
```
db.users.deleteMany({ age: { $lt: 25 } })
```

**Schema Design and Data Modeling**
Designing an efficient schema in MongoDB is crucial, as the data model affects application performance, scalability, and query complexity.

**Embedding vs. Referencing**
MongoDB provides two main ways to model relationships between data: embedding and referencing.

1. Embedding: Stores related data within the same document. This approach is efficient for related data that will be accessed together.
    - Use Case: Storing a user and their address in a single document
    - Example:
```json
    {
  "_id": 1,
  "name": "John",
  "address": {
    "street": "123 Main St",
    "city": "New York",
    "zip": "10001"
  }
}
```
2. Referencing: Stores related data in separate documents and links them using a reference ID. This approach is useful for large datasets and data that changes independently.
    - Use Case: Storing orders with customer IDs instead of embedding the customer data in each order.
    - Example:
```json
// Customer document
{
  "_id": 1,
  "name": "John Doe"
}
// Order document
{
  "_id": 101,
  "customer_id": 1,
  "order_date": "2023-01-15",
  "items": ["item1", "item2"]
}
```

**Denormalization and Data Relationships**

1. One-to-One Relationship: Typically embedded directly within the same document, especially for infrequent updates.
2. One-to-Many Relationship: Can be embedded (if the "many" side is limited) or referenced for large datasets.
3. Many-to-Many Relationship: Often managed through referencing with an intermediate collection linking the two collections.

**Advantages and Trade-offs**

- Embedding: Improves read performance by retrieving all related data in a single query but can lead to data duplication and larger documents.
- Referencing: Reduces document size and avoids duplication, though it may increase the complexity of queries due to the need for manual joins in the application.

# 4. Querying and Aggregation

## Querying in MongoDB

MongoDB’s query language allows for powerful and flexible data retrieval. Here are some fundamental querying techniques.

### Query Selectors and Projection

1. **Basic Find Queries**: Use `find()` to retrieve documents from a collection. Query conditions can be specified using fields and values.
   ```javascript
   db.collection.find({ field: "value" })
2. **Comparison Operators**: MongoDB provides a range of operators for filtering results, including $gt, $gte, $lt, $lte, $eq, $ne.
    - Example: Find documents where age is greater than or equal to 25
```javascript
db.users.find({ age: { $gte: 25 } })
```
3. **Logical Operators**: MongoDB supports logical operators like $and, $or, and $not to combine multiple conditions.
    - Example: Find users who are older than 25 or live in "New York".
```javascript
db.users.find({
  $or: [{ age: { $gt: 25 } }, { city: "New York" }]
})
```
4. **Projection**: Use projection to limit the fields returned in the results, which can improve performance by reducing data transfer.
```
db.users.find({ age: { $gte: 25 } }, { name: 1, age: 1 })
```

**Advanced Query Operators**

MongoDB offers additional operators for more complex queries:
- **Array Operators**: $in, $nin, $all can be used with arrays.
    - Example: Find users interested in both "music" and "traveling".
```
db.users.find({ interests: { $all: ["music", "traveling"] } })
```
- **Element Operators**: $exists, $type are used to filter based on the existence or type of fields.
    - Example: Find documents with an address field
```
db.users.find({ address: { $exists: true } })
```
## Indexing
Indexes play a vital role in optimizing query performance by reducing the number of documents MongoDB needs to scan.

### Purpose of Indexing in MongoDB
Indexes create an ordered data structure that MongoDB uses to quickly search documents. Without indexes, MongoDB scans each document in a collection (a "collection scan") for every query.

### Types of Indexes
1. **Single Field Index**: Indexes a single field. Useful for basic queries.
```javascript
db.users.createIndex({ age: 1 })  // 1 for ascending order
```
2. **Compound Index**: Indexes multiple fields in a specific order.
```javascript
db.users.createIndex({ age: 1, name: -1 })  // -1 for descending order
```
3. **Multikey Index**: Creates an index on fields that hold array values, indexing each element of the array individually.

```javascript
db.users.createIndex({ interests: 1 })
```
4. **Text Index**: Enables full-text search on string fields, supporting searches for text within fields
```javascript
db.articles.createIndex({ content: "text" })
```
5. **Geospatial Index**: Allows efficient querying of geospatial data, such as points and polygons, for location-based queries.
```javascript
db.places.createIndex({ location: "2dsphere" })
```

### Indexing Best Practices
- Only index fields that are frequently used in query conditions.
- Limit the number of indexes to balance query performance and storage overhead.
- Regularly review index performance with the explain() method.


### Aggregation Framework.
The MongoDB Aggregation Framework provides a way to process and transform data within MongoDB, performing calculations and returning computed results.

### Introduction to Aggregations and Pipelines
Aggregations in MongoDB are handled through pipelines, which consist of a series of stages that process and filter data.
>> 1. Pipeline Structure: A pipeline is an array of stages that process data sequentially. Each stage uses a specific operator to transform or filter the data.
```javascript
db.collection.aggregate([
  { $match: { field: "value" } },
  { $group: { _id: "$field", total: { $sum: "$amount" } } }
])
```
>> 2. Common Aggregation Stages:
- $match: Filters documents based on specified criteria (similar to find()).
- $group: Groups documents by a specified key and performs aggregation operations on grouped data.
- $project: Reshapes documents, controlling which fields are returned and performing calculations.
- $sort: Orders the documents in ascending or descending order.
- $limit and $skip: Limits the number of documents returned or skips a specified number.

### Examples of Common Aggregations
1. Filtering with $match:
```javascript
db.orders.aggregate([
  { $match: { status: "shipped" } }
])
```
2. Grouping with $group: Calculate the total order amount by customer.
```javascript
db.orders.aggregate([
  { $group: { _id: "$customerId", totalAmount: { $sum: "$amount" } } }
])
```
3. Projecting Fields with $project: Modify the structure of documents, including only specific fields.
```javascript
db.users.aggregate([
  { $project: { name: 1, yearOfBirth: { $subtract: [2023, "$age"] } } }
])
```
4. Sorting Results with $sort: Sort documents by totalAmount in descending order.
```javascript
db.orders.aggregate([
  { $group: { _id: "$customerId", totalAmount: { $sum: "$amount" } } },
  { $sort: { totalAmount: -1 } }
])
```
5. Combining Stages: Filter, group, and sort documents in one pipeline.
```javascript
db.orders.aggregate([
  { $match: { status: "shipped" } },
  { $group: { _id: "$customerId", totalAmount: { $sum: "$amount" } } },
  { $sort: { totalAmount: -1 } }
])
```

### Building Complex Aggregations
MongoDB’s Aggregation Framework can handle complex pipelines by combining multiple stages. Complex aggregations can involve nested groupings, calculations, and conditionals, making it a powerful tool for data analysis.

Example: Get the top 5 customers by total spending for shipped orders only.
```javascript
db.orders.aggregate([
  { $match: { status: "shipped" } },
  { $group: { _id: "$customerId", totalSpent: { $sum: "$amount" } } },
  { $sort: { totalSpent: -1 } },
  { $limit: 5 }
])
```

# 5. Data Management and Security

## Data Management in MongoDB

Efficient data management in MongoDB involves strategies for backup, restore, and database monitoring to ensure data integrity and availability.

### Backup and Restore

1. **mongodump and mongorestore**: MongoDB provides the `mongodump` and `mongorestore` tools for creating and restoring database backups.
   - **mongodump**: Creates a BSON file backup of a database or collection.
     ```shell
     mongodump --db myDatabase --out /path/to/backup
     ```
   - **mongorestore**: Restores data from a backup created by `mongodump`.
     ```shell
     mongorestore --db myDatabase /path/to/backup/myDatabase
     ```

2. **Automated Backups with MongoDB Atlas**: MongoDB Atlas, the managed cloud platform, provides automated, continuous backups and point-in-time restores, which are ideal for production environments.

3. **Snapshot-Based Backups**: For sharded clusters, MongoDB supports snapshot-based backups, allowing consistent backups of distributed data.

### Data Replication and High Availability

Replication in MongoDB provides redundancy and high availability by copying data across multiple servers.

1. **Replica Sets**: A MongoDB replica set is a group of MongoDB servers that maintain the same data set, ensuring data is available even if one server fails.
   - **Primary Node**: The main server that handles all write operations.
   - **Secondary Nodes**: Replica servers that replicate the data from the primary. In the event of primary failure, an automatic election takes place to choose a new primary.
   - **Arbiter Node**: A node that participates in the election process but does not store data.

   Set up a replica set in MongoDB:
   ```javascript
   rs.initiate({
     _id: "replicaSetName",
     members: [
       { _id: 0, host: "localhost:27017" },
       { _id: 1, host: "localhost:27018" },
       { _id: 2, host: "localhost:27019" }
     ]
   })


2. **Automatic Failover**: In a replica set, MongoDB automatically elects a new primary if the current primary fails, ensuring high availability.

3. **Read Preference**: Secondary replicas can be used to distribute read operations, improving performance for read-heavy applications by offloading reads from the primary.

  - Primary: Default; directs all reads to the primary.
  - Secondary: Directs reads to secondary nodes, potentially with eventual consistency.
  - PrimaryPreferred and SecondaryPreferred: Allows reads from secondary if primary is unavailable, or vice versa.

### Security in MongoDB
Securing a MongoDB deployment is crucial for protecting sensitive data and maintaining compliance.

### Authentication
Authentication verifies the identity of users or applications attempting to access MongoDB. By default, MongoDB does not enable authentication, so it is essential to configure it for production environments.
1. **Enable Authentication**: Modify the MongoDB configuration file (mongod.conf) to require authentication.
```yaml
security:
  authorization: "enabled"

```
2. **Create User Roles**: MongoDB provides built-in roles for managing access and permissions, including read, readWrite, dbAdmin, and userAdmin.
  - Example: Create an admin user with access to all databases
```javascript
use admin
db.createUser({
  user: "adminUser",
  pwd: "securePassword",
  roles: [ { role: "userAdminAnyDatabase", db: "admin" } ]
})
```
3. **Role-Based Access Control (RBAC)**: MongoDB uses RBAC to control access to databases and operations based on user roles. Assign only necessary roles to limit access.


### Authorization
Authorization controls what authenticated users can do in MongoDB. Once authentication is enabled, configure user roles and permissions.
1. Assigning Roles to Users: Roles define what actions users can perform and on which databases or collections.
  - Example: Create a user with read and write access to a specific database
```javascript
use myDatabase
db.createUser({
  user: "appUser",
  pwd: "appUserPassword",
  roles: [ { role: "readWrite", db: "myDatabase" } ]
})
```
2. Custom Roles: Define custom roles for specific permissions if the built-in roles are too restrictive or permissive.
```javascript
db.createRole({
  role: "customRole",
  privileges: [
    { resource: { db: "myDatabase", collection: "" }, actions: ["find", "insert"] }
  ],
  roles: []
})
```

### Network Security
Network security practices in MongoDB help prevent unauthorized access from external networks.

1. **Bind IP Address**: Configure MongoDB to listen only on specific IP addresses by modifying bindIp in the configuration file.
```yaml
net:
  bindIp: 127.0.0.1  # Local connections only
```
2. **Firewall Configuration**: Use firewalls to restrict access to MongoDB, only allowing trusted IP addresses.

3. **Transport Encryption (TLS/SSL)**: MongoDB supports TLS/SSL encryption to secure data in transit, especially important for data transmitted over public networks.
  - Enable TLS/SSL in the MongoDB configuration
```yaml
net:
  ssl:
    mode: requireSSL
    PEMKeyFile: /path/to/ssl_certificate.pem
```

### Auditing and Monitoring
Monitoring and auditing provide visibility into database activity and help detect potential security threats.
1. **MongoDB Monitoring Tools**: MongoDB Atlas provides built-in monitoring tools to track performance, query usage, and server status. For self-hosted instances, consider using tools like MongoDB Ops Manager or integrating with external monitoring solutions like Prometheus and Grafana.

2. **Auditing**: MongoDB Enterprise offers auditing capabilities to log database activities, including user access, read/write operations, and configuration changes. Enable auditing in MongoDB to track and review database activity.


# 6. MongoDB Administration

## MongoDB Deployment Strategies

MongoDB can be deployed in various configurations to meet different performance, scalability, and high-availability needs.

1. **Standalone Deployment**: 
   - A single MongoDB server instance, best suited for development and testing but not recommended for production.
   - Easy setup, but lacks redundancy and fault tolerance.

2. **Replica Set Deployment**:
   - A primary-replica deployment model to ensure high availability and data redundancy.
   - At least three nodes are recommended: one primary and two secondaries.
   - Primary handles all writes; secondaries replicate data from the primary.
   - Automatic failover ensures continuity if the primary node fails.

3. **Sharded Cluster Deployment**:
   - A horizontal scaling model for distributing data across multiple servers (shards).
   - Includes three main components:
     - **Shards**: Store the actual data.
     - **Config Servers**: Maintain metadata for the cluster.
     - **Query Routers (mongos)**: Route queries to the appropriate shards.
   - Ideal for large-scale applications requiring high throughput and large datasets.
   - Sharding splits data into ranges based on a shard key, distributing data across shards to balance the load.

---

## Managing Replica Sets

Replica sets are the foundation for high availability in MongoDB. Admins manage replica sets to ensure consistent data replication and availability.

1. **Adding Members to a Replica Set**:
   - To add a new secondary member to an existing replica set:
     ```javascript
     rs.add("hostname:port")
     ```

2. **Removing Members**:
   - Removing a member:
     ```javascript
     rs.remove("hostname:port")
     ```

3. **Changing Member Roles**:
   - Modify a replica set member’s priority to control its likelihood of being elected primary.
     ```javascript
     rs.reconfig({
       _id: "rs0",
       members: [
         { _id: 0, host: "localhost:27017", priority: 2 },
         { _id: 1, host: "localhost:27018", priority: 0.5 }
       ]
     })
     ```

4. **Replica Set Failover and Elections**:
   - If the primary node fails, an automatic election occurs to select a new primary from the secondaries.
   - Admins can trigger an election manually if necessary:
     ```javascript
     rs.stepDown()
     ```

---

## Sharding Administration

Sharding allows MongoDB to scale horizontally across distributed data stores, improving performance and handling large datasets.

1. **Enabling Sharding on a Database**:
   - Enable sharding on the target database.
     ```javascript
     sh.enableSharding("myDatabase")
     ```

2. **Choosing a Shard Key**:
   - Select a field (or combination of fields) as the shard key to determine data distribution.
   - A good shard key should ensure an even data distribution and account for query patterns.

3. **Sharding a Collection**:
   - Shard a collection by specifying a shard key.
     ```javascript
     sh.shardCollection("myDatabase.myCollection", { shardKeyField: 1 })
     ```

4. **Managing Shard Balancing**:
   - MongoDB automatically balances data across shards. Use the balancer to ensure even distribution.
   - To manually control the balancer:
     ```javascript
     sh.startBalancer()
     sh.stopBalancer()
     ```

5. **Moving Chunks**:
   - Admins can manually move chunks (ranges of data) between shards for fine-tuned data distribution.
     ```javascript
     sh.moveChunk("myDatabase.myCollection", { shardKeyField: value }, "targetShard")
     ```

---

## Monitoring and Performance Tuning

Effective MongoDB administration involves continuous monitoring and performance tuning to optimize database performance.

### Monitoring Tools

1. **MongoDB Atlas**: 
   - Managed cloud-based solution with built-in monitoring dashboards.
   
2. **MongoDB Cloud Manager and Ops Manager**:
   - Offer insights on performance metrics, memory usage, CPU load, and index efficiency.
   - Support automated backups and point-in-time recovery.

3. **Third-Party Monitoring**:
   - Tools like **Prometheus**, **Grafana**, or **New Relic** can be integrated with MongoDB for custom monitoring setups.

### Key Performance Metrics

1. **CPU and Memory Usage**: Track resource consumption to understand load patterns and adjust configurations accordingly.
2. **Disk I/O**: Monitor read/write operations, ensuring adequate IOPS (Input/Output Operations Per Second) for high-performance applications.
3. **Network Throughput**: Identify network bottlenecks, especially for distributed environments like sharded clusters.
4. **Operation Latency**: Track the time taken by CRUD operations to diagnose slow queries or data processing issues.

### Tuning Strategies

1. **Optimize Queries**: 
   - Use `explain()` to analyze query execution and identify inefficient queries.
     ```javascript
     db.collection.find({ field: "value" }).explain()
     ```

2. **Index Optimization**:
   - Ensure that frequently queried fields have appropriate indexes.
   - Use compound indexes for queries involving multiple fields.

3. **Cache Management**:
   - Increase the WiredTiger cache size to improve read/write performance.
     - Example: Set cache size in `mongod.conf`.
       ```yaml
       storage:
         wiredTiger:
           engineConfig:
             cacheSizeGB: 2
       ```

4. **Adjust Connection Limits**:
   - Configure connection limits based on workload to avoid overloading the server.
   - Example: Set `maxIncomingConnections` in `mongod.conf`.

---

## Backup and Recovery

Reliable backups are essential for MongoDB administration to prevent data loss.

1. **Automated Backups**:
   - MongoDB Atlas provides automated backups with point-in-time restore capabilities.

2. **Snapshot-Based Backups for Sharded Clusters**:
   - For sharded clusters, use snapshot-based backups to capture consistent backups across distributed data.
   
3. **File-System-Based Backups**:
   - Use filesystem snapshots for a consistent backup of the data directory.
   - For replica sets, take snapshots from secondary nodes to avoid impacting the primary’s performance.

4. **Restoring Data**:
   - To restore a backup created with `mongodump`, use `mongorestore`:
     ```shell
     mongorestore --db myDatabase /path/to/backup
     ```

---

## Database Maintenance Tasks

Routine maintenance tasks are necessary to keep MongoDB databases running smoothly and efficiently.

1. **Compact Databases**:
   - Compaction reclaims unused space in the database after deletes or updates.
   - Use the `compact` command to manually trigger compaction on collections.
     ```javascript
     db.runCommand({ compact: "myCollection" })
     ```

2. **Validate Collections**:
   - Validate the integrity of collections, which is useful for detecting issues.
     ```javascript
     db.runCommand({ validate: "myCollection" })
     ```

3. **Database Profiler**:
   - The MongoDB profiler helps track slow queries and identify inefficient operations.
   - Enable the profiler:
     ```javascript
     db.setProfilingLevel(1, { slowms: 100 })
     ```

4. **Rotate Logs**:
   - Regular log rotation prevents log files from consuming too much disk space.
   - MongoDB supports manual log rotation.
     ```shell
     db.adminCommand({ logRotate: 1 })
     ```

5. **Reindex Collections**:
   - Periodically reindex collections to optimize query performance.
     ```javascript
     db.myCollection.reIndex()
     ```

---
