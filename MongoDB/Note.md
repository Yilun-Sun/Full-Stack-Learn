<p dir='rtl' align='right'><a href="https://github.com/Yilun-Sun/Full-Stack-Learn/blob/master/README.md"> README.md➡</a></p>

## What is MongoDB?

- a database
- schemaless

### Structure:

```
└─document
    └─collection
        ├─record
        ├─record
        │  └─record
        └─record
    └─collection
    └─collection
└─document
```

### Document:

- store multiple collections

### Collection:

- store multiple records

### Record:

- record could nested in another record

## CRUD operations

### Create Operations

Create or insert operations add new documents to a collection. If the collection does not currently exist, insert operations will create the collection.

```
db.collection.insertOne()
db.collection.insertMany()
```

### Read Operations

Read operations retrieves documents from a collection; i.e. queries a collection for documents. MongoDB provides the following methods to read documents from a collection:

```
db.collection.find()
```

### Update Operations

Update operations modify existing documents in a collection. MongoDB provides the following methods to update documents of a collection:

```
db.collection.updateOne()
db.collection.updateMany()
db.collection.replaceOne()
```

### Delete Operations

Delete operations remove documents from a collection. MongoDB provides the following methods to delete documents of a collection:

```
db.collection.deleteOne()
db.collection.deleteMany()
```

## using with C# driver
