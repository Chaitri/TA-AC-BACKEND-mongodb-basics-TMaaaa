writeCode

Write code to:-

- create a database named `mountains`

```
use mountains
```

- a collection inside that database named `himalayas`

```
db.createCollection('himalayas')
```

- insert 1 document into that collection `{name: 'Dhauldhar range', height: '4000 mtrs'}`

```
db.himalayas.insertOne({name: 'Dhauldhar range', height: '4000 mtrs'})
```

- insert multiple document using insertMany command

```
db.himalayas.insertMany([{name: 'Mount Everest', height: '8848 mtrs'}, {name: 'Kanchenjunga', height: '8586 mtrs'}]);
```

- find all documents from mountains

```
db.himalayas.find()
```

- find a single document using name

```
db.himalayas.findOne({name: 'Mount Everest'})
```
