# MongoDB Cheatsheet

## Database
```bash
# List databases
show dbs

# Enter a database
use database_example

# Show the collections inside database_example
show collections
```

## Find
```bash
# 'db.' automatically references the database you entered with 'use'

# Find everything under a specific collection that satisfies this query
db.collection_name.find({"name": "alex"})

# Count the number of documents returned by find
db.collection_name.find({"name": "alex"}).count()

# Output the query result in a more human redable style
db.collection_name.find({"name": "alex"}).pretty()
```
