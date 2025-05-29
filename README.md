# Mongo

Here we will start by creating a database by name:"TODO"
use TODO
![image](https://github.com/user-attachments/assets/1e592124-1fe5-4f1c-91c1-1efd9d066dfd)

then after we will insert the data one by one or all at a time .
here i will use the command:
db.task.insertmany([])
![image](https://github.com/user-attachments/assets/a5033df8-f29b-4d54-bad1-8218c0cfe29c)
then we will abke to see the records by command:
db.task.find({ Status: true }).pretty()
here i added IST to time .First i have just number after that i have added it by command.
![image](https://github.com/user-attachments/assets/523c8933-f552-4660-a64c-e70d81350071)
then by object i set the status true or false command:
const collectionName = "task"; 
const coll = db.getCollection(collectionName);
const idString = "6836d571ac76a7a5e03bab01";
const id = ObjectId(idString);
coll.updateOne(
  { _id: id },
  { $set: { Status: true } }
);
here i update the collection  by created time and uodated time:
![image](https://github.com/user-attachments/assets/c3282c68-751c-4243-a0cb-cc7e5ba02aaf)
by these I counted the items in collections.
db.task.countDocuments({});
![image](https://github.com/user-attachments/assets/188c7663-4562-4860-bac6-6dc251053069)


