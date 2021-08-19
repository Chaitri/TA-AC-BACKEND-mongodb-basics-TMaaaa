writeCode

Write code to:-

- create a database named `sports`.

```
use sports
```

- list all databases present in local mongod server.

```
show dbs
```

- create 3 collections named `cricket`, `football`, `TT` in sports databse.

```
db.createCollection('cricket')
db.createCollection('football')
db.createCollection('TT')
```

- add multiple players in those collections which should have fields like `name`, `age` and `email` and `bid_price`.

```
db.cricket.insertMany([{name: 'saj', age: 28, email: 'sag@gmail.com', bid_price: 1000}, {name: 'raj', age: 27, email: 'raj@gmail.com', bid_price: 1500}, {name: 'ahn', age: 29, email: 'ahn@gmail.com', bid_price: 2000}])

db.football.insertMany([{name: 'ren', age: 18, email: 'ren@gmail.com', bid_price: 1000}, {name: 'ben', age: 27, email: 'ben@gmail.com', bid_price: 1500}, {name: 'sol', age: 22, email: 'sol@gmail.com', bid_price: 2000}])

db.TT.insertMany([{name: 'su', age: 28, email: 'su@gmail.com', bid_price: 1000}, {name: 'may', age: 25, email: 'may@gmail.com', bid_price: 1500}, {name: 'jane', age: 23, email: 'jane@gmail.com', bid_price: 2000}])
```

- list all collections in sports database.

```
show collections
```

- rename `TT` collection to `tennis`.

```
db.TT.renameCollection('tennis')
```

- create a capped collection called `khokho` which should have max 3 documents.
  Try inserting more than 3 and see what happens?

```
db.createCollection('khoko', {capped: true, size: 1024, max: 3})
```
- On inserting more then 3 documents, the oldest documents will be over-written.

- check whether a collection is capped or not?

```
db.khoko.isCapped()
```

- drop all documents from `football` collection.

```
db.football.deleteMany({})
```

- delete cricket collection completely.

```
db.cricket.drop()
```

- delete sports database.

```
db.dropDatabase()
```

- check which database you are connected to ?

```
sports
```

- connect to test database

```
use test
```