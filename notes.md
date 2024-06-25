# Command
- show dbs
- show collections
- use <dbName> if the db is empty, switch it
- db.createCollection("students") => crate
- db.dropDatabase() => delete

- db.students.insertOne({name: 'Sam', age: 30, gpa: 3.2}) => insert
- db.students.find() => show collection
- db.students.insertMany([{}, {}, {}]) => multiple inserts


- db.students.find().sort({name: 1}) 1 => up, -1 => down
- db.students.find().limit(1) => first one 
- db.students.find({gap: 4.0, fullTime: true})
- db.students.find({}, {_id:false, name:true}) => only name
- db.students.find({query}, {projection})

- db.students.updateOne(filter, update)
- db.students.updateOne({ name: "a" }, { $set: { age: 30 } }) => add
- db.students.updateOne({ name: "a" }, { $unset: { age: ""} }) => remove
- db.students.updateMany({}, {$set:{fullTime: false}}) => update
- db.students.updateMany({age:{$exists:false}}, {$set:{fullTime:true}}) = condition update

- db.students.deleteOne({name: ''}) => delete collection

- db.students.find({name:{$ne: "A"}}) => compare => $ne = non
- db.students.find({age:{$lt: 20}}) => $lt = less than
- db.students.find({age:{$lte: 20}}) => $lte = less than and equals
- db.students.find({age:{$gt: 20}}) => $lte = greater than
- db.students.find({age:{$gte: 20}}) => $lte = greater than and equals
- db.students.find({age:{$gte: 20, $lte: 30}}) => between
- db.students.find({name:{$in: ['a', 'c']}}) => in
- db.students.find({name:{$nin: ['a', 'c']}}) => non in

- db.students.find({$and: [{age: true}, {age:{$lte: 29}}]}) => and logical
- db.students.find({$or: [{age: true}, {age:{$lte: 29}}]}) => or logical
- db.students.find({$nor: [{age: true}, {age:{$lte: 29}}]}) => nor logical
- db.students.find({age: {$not: {$gte: 30}}}) => not logical include null value

- db.students.find({name: 'a'}).explain("executionStats") => executionStats
- db.students.createIndex({name: 1}) = index
- db.students.getIndexes() = get
- db.students.dropIndex("name_1") = drop

- db.createCollection("teachers", {capped: true, size: 1000000, max: 100}, {autoIndexId: false})
capped => should be have a size
size => bits
max: => collection limit
- db.teachers.drop() => drop