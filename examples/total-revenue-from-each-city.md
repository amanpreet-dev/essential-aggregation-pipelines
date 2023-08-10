# Total revenue from each city

Based on the sample data, we will find out the total revenue from each city.

## Query

```
db.orders.aggregate([
    {
        $group: {
            _id: "$shippingCity",
            totalRevenue: { $sum: { $multiply: ["$quantity", "$price"] } }
        }
    }
]);
```

## Result

```
[
  {
    "_id": "Los Angeles",
    "totalRevenue": 250
  },
  {
    "_id": "New York",
    "totalRevenue": 3000
  },
  {
    "_id": "San Francisco",
    "totalRevenue": 70
  },
  {
    "_id": "Boston",
    "totalRevenue": 60
  }
]
```
