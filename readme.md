# **Codetribe MongoDB Setup**
### This README outlines the steps and MongoDB shell commands (mongosh) used to create and manage the Codetribe database, including adding collections and inserting documents. It also provides instructions on how to start the MongoDB shell and utilize the commands effectively.

# Prerequisites

1. MongoDB and mongosh (MongoDB shell) must be installed on your system.
2. Starting the MongoDB Shell
3. Open a terminal or command prompt.
4. Start the MongoDB server if it's not running already:


bash
Copy code
`mongod`
Open the MongoDB shell (mongosh):



bash
Copy code
`mongosh`

### You should see a message indicating that you're connected to MongoDB.
`Creating the Database and Collections`
# Follow these steps to create the Codetribe database and add the required collections.

1. Create the Codetribe Database

Switch to the Codetribe database (if it doesn't exist, it will be created automatically):


javascript
Copy code
`use Codetribe`


1.  Create the Collections and Insert Documents
2. Create the Facilitators Collection

Insert a document into the Facilitators collection with the fields Name, Location, and Course:
javascript
Copy code
```
db.Facilitators.insertOne({
    Name: "John Doe",
    Location: "Johannesburg",
    Course: "Full-Stack Development"
})
```
2.2. Create the Trainees Collection
Insert a document into the Trainees collection with the fields Name, Location, and Facilitator:

javascript
Copy code
```
db.Trainees.insertOne({
    Name: "Jane Smith",
    Location: "Pretoria",
    Facilitator: "John Doe"
})
```
2.3. Create the Projects Collection
Insert a document into the Projects collection with the fields Name, Course, and Lesson:

javascript
Copy code
```
db.Projects.insertOne({
    Name: "Weather App",
    Course: "Full-Stack Development",
    Lesson: "React and APIs"
})
```
### Verifying Your Setup
To confirm the data has been inserted correctly, you can run the following commands:

Switch to the Codetribe database:

javascript
Copy code
`use Codetribe`
List all collections:

javascript
Copy code
`show collections`
View documents in each collection:

javascript
Copy code
```
db.Facilitators.find()
db.Trainees.find()
db.Projects.find()
```
Backing Up the Database
To back up the database, you can use the mongodump tool:

bash
Copy code
`mongodump --db=Codetribe --out=/path/to/backup/`
Replace /path/to/backup/ with your desired backup directory.

Restoring the Database
To restore a backup, use the mongorestore tool:

bash
Copy code
`mongorestore --db=Codetribe /path/to/backup/Codetribe`
Replace /path/to/backup/Codetribe with the actual backup path.

# Summary of MongoDB Commands

- use Codetribe: Switches to the Codetribe database.
- db.CollectionName.insertOne({ ... }): Inserts a document into a collection.
- show dbs: Lists all databases.
- show collections: Lists all collections in the current database.
- db.CollectionName.find(): Displays documents in the specified collection.
