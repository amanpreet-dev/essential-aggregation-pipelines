# Sort customers based on the number of items they purchased

Based on the sample data, we will sort the customers based on the number of items they purchased.

## Query

```
db.orders.aggregate([
    {
        $group: {
            _id: "$customerName",
            totalItemsPurchased: { $sum: "$quantity" }
        }
    },
    {
        $sort: { totalItemsPurchased: -1 }
    }
]);
```

## Result

```
[
  {
    "_id": "Alice",
    "totalItemsPurchased": 5
  },
  {
    "_id": "Bob",
    "totalItemsPurchased": 5
  },
  {
    "_id": "Eve",
    "totalItemsPurchased": 1
  },
  {
    "_id": "Charlie",
    "totalItemsPurchased": 1
  }
]
```
