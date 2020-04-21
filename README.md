# mongo_learning


https://www.youtube.com/watch?v=vb8xZ-bvxbg&list=PLLAZ4kZ9dFpOFJ9JcVW9u4PlSWO-VFoao

installing MongoDB Compass comunity edition

/data/db is the default folder structer mongo will use, you can change this unsing mongod --datapath path

Bulk Actions

db.students.bulkWrite(
	[
    {
      insertOne: { "document": {name:"terry", gpa:10 }  }
    },
    {
      updateOne: {}
    },
    {
      deleteOne: {
        filter: {name:"Mike}
      }
    }
	]
)



Aggregation

group
db.purchase_orders.aggregate(
	[
		{ $match: {} },
		{ $group: {_id:"$customer", total: {$sum:"$total"} } },
		{ $sort: {total: -1} }
	]
)
