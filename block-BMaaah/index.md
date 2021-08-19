writeCode

Write code to execute below expressions.

1. Create a database named `blog`.

```js
use blog
```

2. Create a collection called 'articles'.

```js
db.createCollection('articles');
```

3. Insert multiple documents(at least 3) into articles. It should have fields

- title as string
- createdAt as date
- details as String
- author as nested object
  - author should have
    - name
    - email
    - age
    - example author: {name: 'abc', email: 'abc@gmail', age: 25}
- tags : Array of strings like ['html', 'css']

```js
// An article should look like in the database
{
  _id: 'some_random_id',
  title: '',
  details: '',
  author: {
    name: '',
    email: '',
    age: ''
  },
  tags: ['js', 'mongo']
}
```

```js
let articles = [
  {
    title: 'Complete Node Guide',
    details: 'Guide on node - updated 2021',
    author: {
      name: 'ABC',
      email: 'abc@gmail.com',
      age: '32',
    },
    tags: ['js', 'node'],
  },
  {
    title: 'Complete MongoDB Guide',
    details: 'Guide on MongoDB',
    author: {
      name: 'ABC',
      email: 'abc@gmail.com',
      age: '32',
    },
    tags: ['js', 'mongo'],
  },
  {
    title: 'Complete HTML Guide',
    details: 'Guide on HTML',
    author: {
      name: 'XYZ',
      email: 'xyz@gmail.com',
      age: '34',
    },
    tags: ['html'],
  },
];

db.articles.insert(articles);
```

4. Find all the articles using `db.COLLECTION_NAME.find()`

```js
db.articles.find();
```

5. Find a document using \_id field.

```js
db.articles.find({ _id: ObjectId('611e7fd11d032648ba3777cf') });
```

6. 1. Find documents using title

```js
db.articles.find({ title: 'Complete HTML Guide' });
```

7. 2. Find documents using author's name field.

```js
db.articles.find({ 'author.name': 'ABC' });
```

8. Find document using a specific tag.

```js
db.articles.find({ tags: 'js' });
```

9. Update title of a document using its \_id field.

```js
db.articles.updateOne(
  { _id: ObjectId('611e7fd11d032648ba3777d1') },
  { $set: { title: 'Complete HTML and CSS Guide' } }
);
```

10. Update a author's name using article's title.

```js
db.articles.updateOne(
  { title: 'Complete HTML and CSS Guide' },
  { $set: { 'author.name': 'XYZZ' } }
);
```

11. rename details field to description from all articles in articles collection.

```js
db.articles.updateMany({}, { $rename: { details: 'description' } });
```

12. Add additional tag in a specific document.

```js
db.articles.updateOne(
  { title: 'Complete HTML and CSS Guide' },
  { $push: { tags: 'css' } }
);
```

13. Update an article's title using $set and without $set.

- Write the differences here ?

```js
db.articles.updateOne(
  { title: 'Complete HTML and CSS Guide' },
  { $set: { title: 'Complete HTML and CSS Guide - UPDATED 2021' } }
);

db.articles.update(
  { description: 'Guide on HTML' },
  { title: 'Complete HTML and CSS Guide - UPDATED 2021' }
);

// With $set, only the given key-value are replaced; without $set, entire document is over-written.
```

13. find an article using title and increment it's auhtor's age by 5.

```js
db.articles.update(
  { title: 'Complete Node Guide' },
  { $inc: { 'author.age': 5 } }
);
```

14. Delete a document using \_id field with `db.COLLECTION_NAME.remove()`.

```js
db.articles.remove({ title: 'Complete HTML and CSS Guide - UPDATED 2021' });
```

// Sample data

```js
db.users.insertMany([
  {
    age: 49,
    name: 'Maurice Brock',
    email: 'wuk@hibpiz.ch',
    gender: 'Female',
    sports: ['cricket', 'football'],
    scores: [24, 35, 18, 16],
    weight: 45,
  },
  {
    age: 37,
    birthday: '7/15/1986',
    name: 'Virgie Cunningham',
    email: 'ezogafa@de.gm',
    gender: 'Male',
    sports: ['football'],
    scores: [17, 35, 43],
    weight: 52,
  },
  {
    age: 48,
    birthday: '5/14/1961',
    name: 'Alexander Holt',
    email: 'han@mu.pe',
    gender: 'Male',
    sports: ['cricket', 'football', 'TT'],
    scores: [24, 30, 16],
    weight: 55,
  },
  {
    age: 53,
    birthday: '11/15/1963',
    name: 'Derek Dawson',
    email: 'polril@now.de',
    gender: 'Male',
    sports: ['cricket', 'hockey'],
    scores: [20, 15, 38, 23],
    weight: 49,
  },
  {
    age: 34,
    birthday: '7/24/1964',
    name: 'Cynthia Cobb',
    email: 'wujjarpob@jecimpar.gu',
    gender: 'Female',
    sports: ['cricket'],
    scores: [41, 17, 28],
    weight: 51,
  },
  {
    age: 33,
    birthday: '10/26/1982',
    name: 'Isabella Atkins',
    email: 'ononuzas@givhoz.ca',
    gender: 'Female',
    sports: ['cricket', 'football', 'hockey', 'TT'],
    scores: [14, 38, 29, 45, 20],
    weight: 49,
  },
  {
    age: 47,
    birthday: '10/12/1978',
    name: 'Katharine Bryan',
    email: 'zo@pebi.sa',
    gender: 'Male',
    sports: ['TT', 'hockey', 'khokho'],
    scores: [27, 20, 34],
    weight: 58,
  },
  {
    age: 41,
    birthday: '1/28/1991',
    name: 'Beatrice Fleming',
    email: 'ufufsa@pujizren.tk',
    gender: 'Female',
    sports: ['football', 'khokho'],
    scores: [30, 20, 15, 29, 43],
    weight: 47,
  },
  {
    age: 26,
    birthday: '3/23/1998',
    name: 'Tom Fields',
    email: 'wasodjow@ofaba.gf',
    gender: 'Female',
    sports: ['khokho'],
    scores: [37, 29, 18, 43, 49],
    weight: 50,
  },
  {
    age: 33,
    birthday: '11/14/1960',
    name: 'Steve Ortega',
    email: 'dupus@ca.ls',
    gender: 'Female',
    sports: ['cricket', 'football', 'hockey'],
    scores: [12, 15, 20],
    weight: 51,
  },
  {
    age: 24,
    birthday: '1/5/1994',
    name: 'Suraj Kumar',
    weight: 50,
    gender: 'Male',
    sports: ['football', 'cricket', 'TT'],
  },
]);
```

Insert above data into database to perform below queries:-

- Find all males who play cricket.

```js
db.users.find({ gender: 'Male', sports: 'cricket' });
```

- Update user with extra golf field in sports array whose name is "Steve Ortega".

```js
db.users.update({ name: 'Steve Ortega' }, { $push: { sports: 'golf' } });
```

- Find all users who play either 'football' or 'cricket'.

```js
db.users.find({ sports: { $in: ['cricket', 'football'] } });
```

- Find all users whose name includes 'ri' in their name.

```js
db.users.find({ name: /ri/ });
```
