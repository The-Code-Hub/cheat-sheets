# MongoDB Cheatsheet

## Database
```bash
# List databases
show databases
show dbs

# Enter a database
use database_example

# Show current database
db

# Show the collections inside database_example
show collections

# Delete a collection
db.collection_name.drop()
```

## Find
```bash
# 'db.' automatically references the database you entered with 'use'

# Find everything under a specific collection that satisfies this query
db.collection_name.find() # Returns everything
db.collection_name.find({"name": "alex"})

# Count the number of documents returned by find
db.collection_name.find({"name": "alex"}).count()

# Output the query result in a more human redable style
db.collection_name.find({"name": "alex"}).pretty()
```
## Count
```bash
# Count all elements from the collection       
db.collection_name.estimatedDocumentCount()  # estimation based on collection metadata
db.collection_name.countDocuments() # accurate count

# Count elements from a query
db.collection_name.count({"name": "Alex"})
db.collection_name.countDocuments({"name": "Alex"})
```

## Insert
```bash
# Insert values
db.collection_name.insertOne({"name": "paul"}) # Single document
db.collection_name.insertMany([{"name": "leto"}, {"name": "alisson"}]) # Array

# If ordered is true, if an error occurs in one document, the insertion will be canceled
# and other documents that are after the current will not be evaluated and inserted.
# If ordered is false, the insertion will not cancel and add every document that is correct.
db.collection_name.insertMany([{"name": "leto"}, {"name": "alisson"}], {"ordered": false})
```

## Delete
```bash
db.collection_name.deleteMany({}) # Deletes all documents from the collection
db.collection_name.deleteMany({"name": "Alex"}) # Deletes all documents returned by this query

# Delete only one documented contained in this query
db.collection_name.deleteOne({"name": "Alex"})

# Returns the document and delete it
db.collection_name.findOneAndDelete({"name": "Max"}) 
```

## Update
```bash
# Change a value with $set
db.collection_name.updateOne({"_id": 1}, {$set: {"name": "Alice"}})

# Increment a value with $inc
db.collection_name.updateOne({"_id": 1}, {$inc: {"age": 10"}})
```
