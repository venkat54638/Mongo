


The steps to create and manage a TODO database in MongoDB, including creating a database, inserting data, querying records, and updating documents.


## 1. Creating the TODO Database

Here we will start by creating a database by name: "TODO"

```javascript
use TODO
```

![image](https://github.com/user-attachments/assets/1e592124-1fe5-4f1c-91c1-1efd9d066dfd)

## 2. Inserting Data into the Collection

Then after we will insert the data one by one or all at a time. Here I will use the command:

```javascript
db.task.insertMany([])
```

![image](https://github.com/user-attachments/assets/a5033df8-f29b-4d54-bad1-8218c0cfe29c)

## 3. Querying Records

Then we will be able to see the records by command:

```javascript
db.task.find({ Status: true }).pretty()
```

Here I added IST to time. First I had just a number, after that I have added it by command.

![image](https://github.com/user-attachments/assets/523c8933-f552-4660-a64c-e70d81350071)

## 4. Updating Document Status

Then by object I set the status true or false command:

```javascript
const collectionName = "task"; 
const coll = db.getCollection(collectionName);
const idString = "6836d571ac76a7a5e03bab01";
const id = ObjectId(idString);
coll.updateOne(
  { _id: id },
  { $set: { Status: true } }
);
```
## 5. Updating by adding the createdtime and updatedtime

Then here we will add the createdtime and updated time to it:

```javascript
db.task.find().forEach(doc => {
  
  if (doc.hasOwnProperty("Status")) {
    let newStatus = !doc.Status; // Simulate a status change

    db.task.updateOne(
      { _id: doc._id },
      {
        $set: {
          Status: newStatus,
          updatedTime: new Date()
        }
      }
    );
  }
});
```

![image](https://github.com/user-attachments/assets/8b499d8d-400e-40b7-abbb-b9558ed51407)

