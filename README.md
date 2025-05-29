MongoDB TODO Database Operations
This document outlines the steps to create and manage a TODO database in MongoDB, including creating a database, inserting data, querying records, updating documents, and counting items in the collection.
1. Creating the TODO Database
To create a database named TODO in MongoDB, use the following command:
use TODO

2. Inserting Data into the Collection
To insert multiple documents into the task collection, use the insertMany command:
db.task.insertMany([])

3. Querying Records
To retrieve tasks with a specific status (e.g., Status: true), use the find command with the pretty method for formatted output:
db.task.find({ Status: true }).pretty()

Adding IST to Timestamps
Timestamps were initially stored as numbers and later updated to include Indian Standard Time (IST) using appropriate commands.
4. Updating Document Status
To update the Status field of a specific document in the task collection, use the updateOne command with the document's _id:
const collectionName = "task"; 
const coll = db.getCollection(collectionName);
const idString = "6836d571ac76a7a5e03bab01";
const id = ObjectId(idString);
coll.updateOne(
  { _id: id },
  { $set: { Status: true } }
);

5. Updating Timestamps
The CreatedTime and UpdatedTime fields were updated for documents in the task collection using appropriate commands.
6. Counting Documents in the Collection
To count the total number of documents in the task collection, use the countDocuments command:
db.task.countDocuments({});

Summary
The above commands demonstrate how to:

Create and switch to the TODO database.
Insert multiple task documents into the task collection.
Query tasks based on their status.
Update the status and timestamps of specific documents.
Count the total number of documents in the collection.

