## 1. Inserting multiple documents

```
// Inserting multiple documents
const documents = [
            {
              name: 'John Doe',
              age: 30,
              gender: 'Male',
              address: ['123 Main St', 'Apt 301'],
              education: { ssc: 'Science', hsc: 'Science' }
            },
            {
              name: 'Jane Smith',
              age: 28,
              gender: 'Female',
              address: ['456 Oak Ave', 'Suite 102'],
              education: { ssc: 'Science', hsc: 'Science' }
            }
        ];

const insertResult = await collection.insertMany(documents);
console.log(`${insertResult.insertedCount} documents inserted`);
```

## 2. Inserting a single document

```
const insertOneResult = await collection.insertOne({
            name: 'Michael Brown',
            age: 25,
            gender: 'Male',
            address: ['789 Elm St', 'Unit B'],
            education: { ssc: 'Science', hsc: 'Science' }
        });
console.log(`Inserted ID: ${insertOneResult.insertedId}`);
```
## 3. Finding documents

```
const findResult = await collection.find({}).toArray();
console.log('All documents:');
console.log(findResult);

```
## 4. Finding one document

```
const findOneResult = await collection.findOne({ name: 'John Doe' });
console.log('Found document:');
console.log(findOneResult);
```
## 5. Field filtering (excluding _id field)

```
const filteredResult = await collection.find({}).project({ _id: 0 }).toArray();
console.log('Filtered documents (excluding _id field):');
console.log(filteredResult);
```


