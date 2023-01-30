# CRUD Operations

### Creating Documents

<br>

`db.<collectionName>.insertMany([{ name: "The Sea Explorer", price: 497, rating: 4.8 }, { name: "The Snow Adventurer", price: 997, rating: 4.9, difficulty: "easy"}])`

- Use `db.<collectionName>.find()` will list Mongo BSON

<br>

### Quering Documents

<br>

1. Getting only one field in BSON

   - matches the given condition in find()

     `db.<collectionName>.find({ name: "The Forest Hiker" })`

<br>

2.  Getting given field with specified condition

    - 'lte' stands for Less than or Equal to

      `db.<collectionName>.find({ price: {$lte: 500} })`

<br>

3.  Getting given field with many conditions

    - 'lt' stands for less than

    - 'gte' stands for greater than or equal to

      `db.<collectionName>.find({ price: {$lt: 500}, rating: {$gte: 4.8}  })`

<br>

4. Getting field with using AND/OR Operator

   - '$or' means only one object in given array needs to be true

     `db.<collectionName>.find({ $or: [{price: {$lt: 500}}, {rating: {$gte: 4.8}}] })`

<br>

### Updating Documents

<br>

1.  Updating single document

    - '$set' means updating that field to the provided ones

      `db.<collectionName>.updateOne({name: "The Snow Adventurer"}, {$set: {price: 597}})`

<br>

2.  Updating many documents

    - If document is not exist to update '$set' will create new document and sets its value to the given one

      `db.<collectionName>.updateMany({price: {$gt: 500}, rating: {$gte: 4.9}}, {$set: {premium: true}})`

<br>

3. Replacing document

   - Refer Docs for this

     `db.<collectionName>.replaceOne()`

<br>

### Deleting Documents

<br>

1. Deleting with given condition

   - Deletes document with given condition

     `db.<collectionName>.deleteMany({rating: {$lt: 4.8}})`

<br>

2. Deleting all documents

   - Deletes entire documents present in the collection

   - Irreversible

     `db.<collectionName>.deleteMany({})`

<br>
