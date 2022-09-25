writeCode

Write command to

- List collections from a database.
  show collections

- create a new collection in your country database which you created recently.
  db.createCollection("bhopal")

Write code to:-

- crate a database named `weather`
  use weather

- create a capped collection named `temperature` with maximum of 3 documents and try inserting more than 3 to see the result.
  db.createCollection("temperature",{capped:true,size:1024,max:3})
  db.temperature.insert({"mumbai":32})
  db.temperature.insert({"bhopal":31})
  db.temperature.insert({"goa":30})
  db.temperature.insert({"delhi":28})

- create a simple collection named `humidity`
  db.createCollection("humidity")

- check whether `temperature` collection is capped or not ?
  db.temperature.isCapped()

- Delete `humidity` collection and then the entire database(weather).
  db.humidity.drop()
  db.dropDatabase()
