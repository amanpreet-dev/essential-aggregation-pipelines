# Filter orders that exceed a certain price e.g $500

Based on the sample data, we will find out the orders for which the total price exceeds $500.

## Query

```
db.orders.aggregate([
    {
        $project: {
            orderValue: { $multiply: ["$quantity", "$price"] },
            product: 1,
            customerName: 1
        }
    },
    {
        $match: {
            orderValue: { $gt: 500 }
        }
    }
]);
```

## Result

```
[
  {
    "_id": 1,
    "customerName": "Alice",
    "orderValue": 2000
  },
  {
    "_id": 3,
    "customerName": "Charlie",
    "orderValue": 1000
  }
]
```

Please note we require the total order price and not the total order value. So we will use the $project stage to calculate the order value and then use the $match stage to filter the orders that exceed $500.
