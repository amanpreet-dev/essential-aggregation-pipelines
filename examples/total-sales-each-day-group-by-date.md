# Group by date to find the total sales for each day

Based on the sample data, we will find out the total sales for each day.

## Query

```
db.orders.aggregate([
    {
        $group: {
            _id: "$orderDate",
            totalSalesForTheDay: { $sum: { $multiply: ["$quantity", "$price"] } }
        }
    }
]);
```

## Result

```
[
  {
    "_id": "2023-08-05",
    "totalSalesForTheDay": 1250
  },
  {
    "_id": "2023-08-08",
    "totalSalesForTheDay": 60
  },
  {
    "_id": "2023-08-01",
    "totalSalesForTheDay": 2000
  },
  {
    "_id": "2023-08-09",
    "totalSalesForTheDay": 70
  }
]
```
