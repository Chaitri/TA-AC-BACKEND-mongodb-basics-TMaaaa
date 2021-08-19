writeCode

Write command to

- List collections from a database.

show collections

- create a new collection in your country database which you created recently.

use india
db.createCollection('states')

Write code to:-

- crate a database named `weather`

use weather

- create a capped collection named `temperature` with maximum of 3 documents and try inserting more than 3 to see the result.

db.createCollection('temperature', {capped: true, size: 4096, max: 3})
db.temperature.insertOne({bangalore: 32})
db.temperature.insertOne({kollam: 35})
db.temperature.insertOne({chennai: 38})

When extra records are inserted, the previous ones will be replaced. The oldest record will be over-written, and a max of only 3 records will be present.

- create a simple collection named `humidity`

db.createCollection('humidity')

- check whether `temperature` collection is capped or not ?

db.temperature.isCapped()

- Delete `humidity` collection and then the entire database(weather).

db.humidity.drop()
db.dropDatabase()