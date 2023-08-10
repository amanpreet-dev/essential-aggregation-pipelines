# essential-aggregation-pipelines

This repo is showing the examples for the top 5 essential aggregation pipelines in MongoDB

## Examples are based on the MongoDB version 6.0

You can install MongoDB version 6.0 from [here](https://www.mongodb.com/try/download/community) and can also use the [MongoDB Atlas](https://www.mongodb.com/cloud/atlas) to try out these examples.

## Sample Data

We will be using 2 sample data sets for this demo.

The first one is the [products](data/products.json) dataset and second one is the [orders](data/orders.json) sample dataset. Both of these datasets are available in the data folder.

## Top 5 Essential Aggregation Pipelines

- $match
- $group
- $project
- $lookup
- $unwind

## Some More Aggregation Examples

Below are some more aggregation examples that you can try out.

- [Calculate Total Sales for Each Product Spec](examples/total-sales-each-product.md)
- [Group by date to find the total sales for each day](examples/total-sales-each-day-group-by-date.md)
- [Filter orders that exceed a certain price](examples/filter-orders-exceed-a-price)
- [Find out the total revenue from each city](examples/total-revenue-each-city.md)
- [Sort customers based on the number of items they purchased](examples/sort-customers-based-on-items-purchased.md)

## How to run the examples

You can run the examples by using the MongoDB Playground. You can follow the instructions [here](https://mongoplayground.net/) to get started with MongoDB Playground.
