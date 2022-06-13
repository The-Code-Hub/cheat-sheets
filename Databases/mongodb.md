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
db.collection_name.insertOne({"name": "paul"}) # Single element
db.collection_name.insertMany([{"name": "leto"}, {"name": "alisson"}]) # Array
```

## Delete
```bash
db.collection_name.remove({}) # Remove all documents from the collection
db.collection_name.remove({"name": "Alex"}) # Remove a specific document
db.collection_name.findOneAndDelete({"name": "Max"}) # Returns the document and delete it
```