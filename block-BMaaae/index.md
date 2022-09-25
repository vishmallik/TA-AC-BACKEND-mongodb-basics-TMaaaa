writeCode

Write code to :-

- create a database named `sports`.
  use sports

- list all databases present in local mongod server.
  show dbs

- create 3 collections named `cricket`, `football`, `TT` in sports databse.
  db.createCollection("cricket")
  db.createCollection("football")
  db.createCollection("TT")

- add multiple players in those collections which should have fields like `name`, `age` and `email` and `bid_price`.
  db.cricket.insertMany([{name:'Sachin',age:35,email:'sachin@gmail.com',bid_price:300000},{name:'Dhoni2',age:35,email:'dhoni@gmail.com',bid_price:235022}])
  db.football.insertMany([{name:"ronaldo",age:36,email:"ronaldo@gmail.com",bid_price:522245},{name:"Messi",age:34,email:"messi@gamil.com",bid_price:223225}])
  db.TT.insertMany([{name:"Suresh",age:27,email:"suresh@gmail.com",bid_price:222554},{name:"shalini",age:28,email:"shalini@gmail.com",bid_price:45455}])

- list all collections in sports database.
  show collections

- rename `TT` collection to `tennis`.
  db.TT.renameCollection("tennis")

- create a capped collection called `khokho` which should have max 3 documents.
  db.createCollection("khokho",{capped:true,size:1024,max:3})

  Try inserting more than 3 and see what happens?
  db.khokho.insertMany([{player1:"Raj"},{player2:"Anjali"},{player3:"Shahrukh"}])

  db.khokho.find()

  //Output
  [
  { _id: ObjectId("63304848271219952fe76b6c"), player1: 'Raj' },
  { _id: ObjectId("63304848271219952fe76b6d"), player2: 'Anjali' },
  { _id: ObjectId("63304848271219952fe76b6e"), player3: 'Shahrukh' }
  ]

  db.khokho.insert({player4:"Akshay"})

  db.khokho.find()
  //Output
  [
  { _id: ObjectId("63304848271219952fe76b6d"), player2: 'Anjali' },
  { _id: ObjectId("63304848271219952fe76b6e"), player3: 'Shahrukh' },
  { _id: ObjectId("63304871271219952fe76b6f"), player4: 'Akshay' }
  ]

  //Since collection is capped only 3 documents are allowed that why player first got popped and new player4 was inserted

- check whether a collection is capped or not?
  db.khokho.isCapped() //true

- drop all documents from `football` collection.
  db.football.remove({})

- delete cricket collection completely.
  db.cricket.drop()

- delete sports database.
  db.dropDatabase()

- check which database you are connected to ?
  db

- connect to test database
  use test
