# MongoDB Guide

## Overview

MongoDB is a **NoSQL document-oriented database** designed for high performance, high availability, and scalability.
Unlike relational databases that store data in tables, MongoDB stores data in **documents** using a JSON-like structure called **BSON (Binary JSON)**.

MongoDB is commonly used in modern web applications, data analytics systems, and distributed architectures.

---

## Key Features

### Document-Oriented Storage

MongoDB stores data in flexible documents instead of rows and columns.

Example document:

```json
{
  "name": "Bhavan",
  "age": 21,
  "skills": ["Python", "Machine Learning", "MongoDB"]
}
```

---

### Schema Flexibility

MongoDB collections do not require a fixed schema.

Example:

```json
{ "name": "Alice", "age": 25 }
{ "name": "Bob", "email": "bob@gmail.com" }
```

Both documents can exist in the same collection.

---

### Horizontal Scalability

MongoDB supports **sharding**, which distributes data across multiple servers for handling large datasets.

---

### High Availability

MongoDB provides **replica sets**, which maintain multiple copies of data for fault tolerance and automatic failover.

---

## MongoDB Architecture

```
MongoDB Server
│
├── Database
│     ├── Collection
│     │      ├── Document
│     │      ├── Document
│     │      └── Document
```

Example structure:

```
company_db
 └── employees
      ├── {name:"Alice", role:"Engineer"}
      ├── {name:"Bob", role:"Manager"}
```

---

## Installation

### Windows

1. Download MongoDB Community Edition.
2. Run the installer.
3. Add MongoDB to system PATH.
4. Verify installation.

```bash
mongosh
```

---

## Connecting to MongoDB Atlas

MongoDB Atlas is the **cloud-hosted version of MongoDB**.

Connection command:

```bash
mongosh "mongodb+srv://username:password@cluster.mongodb.net/"
```

Example:

```bash
mongosh "mongodb+srv://bhavan:password123@cluster.mongodb.net/"
```

---

## Basic MongoDB Shell Commands

### Show Databases

```javascript
show dbs
```

### Use Database

```javascript
use myDatabase
```

### Show Collections

```javascript
show collections
```

### Insert Document

```javascript
db.users.insertOne({
  name: "John",
  age: 30
})
```

### Find Documents

```javascript
db.users.find()
```

### Update Document

```javascript
db.users.updateOne(
  { name: "John" },
  { $set: { age: 31 } }
)
```

### Delete Document

```javascript
db.users.deleteOne({ name: "John" })
```

---

## Example Query

Find users older than 25:

```javascript
db.users.find({ age: { $gt: 25 } })
```

---

## Sample Datasets

MongoDB Atlas provides sample databases for practice:

* `sample_mflix`
* `sample_airbnb`
* `sample_weatherdata`
* `sample_training`

Example query:

```javascript
use sample_mflix
db.movies.find().limit(5)
```

---

## Advantages

* Flexible schema
* High scalability
* Easy integration with modern applications
* Suitable for large-scale distributed systems

---

## Limitations

* No strict schema enforcement
* Complex joins are harder compared to relational databases

---

## Common Use Cases

* Real-time analytics
* Content management systems
* IoT platforms
* Mobile applications
* E-commerce systems

---

## Tools in MongoDB Ecosystem

* MongoDB Compass – GUI for database management
* MongoDB Atlas – Cloud-hosted MongoDB service
* mongosh – MongoDB shell
* Mongoose – ODM library for Node.js

---

## License

This project is created for educational and demonstration purposes.
