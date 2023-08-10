# Total Sales for Each Product Spec

Based on the sample data, we will find out the total sales for each product spec.

## Query

```
db.orders.aggregate([
    {
        $lookup: {
            from: "products",
            localField: "productId",
            foreignField: "_id",
            as: "productDetails"
        }
    },
    {
        $unwind: "$productDetails"
    },
    {
        $unwind: "$productDetails.specs"
    },
    {
        $group: {
            _id: "$productDetails.specs",
            totalSales: {
                $sum: {
                    $multiply: [
                        "$quantity",
                        "$price"
                    ]
                }
            }
        }
    }
])
```

## Result

```
[
  {
    "_id": "Bluetooth",
    "totalSales": 250
  },
  {
    "_id": "Wireless",
    "totalSales": 60
  },
  {
    "_id": "Intel i7",
    "totalSales": 3000
  },
  {
    "_id": "Optical",
    "totalSales": 60
  },
  {
    "_id": "Mechanical",
    "totalSales": 70
  },
  {
    "_id": "512GB SSD",
    "totalSales": 3000
  },
  {
    "_id": "RGB Backlit",
    "totalSales": 70
  },
  {
    "_id": "8hr Battery",
    "totalSales": 250
  },
  {
    "_id": "Noise Cancelling",
    "totalSales": 250
  },
  {
    "_id": "16GB RAM",
    "totalSales": 3000
  }
]
```
