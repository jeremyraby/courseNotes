# SQL Basics

## Basic Elements of a Query

| Purpose           | Clause   | Example |
| ---               | ---      | ---     |
| To choose columns | SELECT   | name, MIN(year) AS oldest_work_from |
| To choose a table | FROM     | artworks |
| To join a table   | JOIN     | artists |
|                   | ON       | artworks.artist_id = artists.id |
| To filter records | WHERE    | title != 'The Mona Lisa' |
| To group records  | GROUP BY | name |
| To filter groups  | HAVING   | MIN(year) < 1700 |
| To sort output    | ORDER BY | MIN(year); |

## Order of Operations

SQL queries have an order of operations similar to algebraic equations. The order may change depending on which clauses are used in the query, but generally speaking the order is:

1. FROM
2. JOIN
3. WHERE
4. GROUP BY
5. HAVING
6. SELECT
7. ORDER BY

## The GROUP BY clause

`GROUP BY` allows you to put multiple rows of data with the same column name into the same "group". The result table will have a column for the "groups" and at least one other column containg data about those groups (like how many are in the group). Imagine you have a big box of different colored candies - some are red, some are blue, and some are green. If you want to know how many of each color there are, you could group them together by color, right?

SQL's GROUP BY clause works in a similar way. Let's say you have a big table of data with different items and their prices, and you want to know how much money you've made from selling each type of item. You can use the GROUP BY clause to group all the items with the same name together, and then SQL will show you the total price for each group.

In general, you can use any column or combination of columns in a GROUP BY clause as long as the values in that column or combination of columns uniquely identify each group you want to create. However, you should be careful not to include columns that don't contribute to the uniqueness of the group. Just be sure to include the grouping column in the `SELECT` clause.

Using the following table `sales`:

| item | price |
| ---  | ---   |
| cookie | 1.00 |
| cookie | 1.00 |
| cookie | 1.50 |
| cupcake | 2.50 |
| cupcake | 3.00 |
| brownie | 3.00 |
| brownie | 3.50 |
| brownie | 4.00 |

This query will return the following result table:

`SELECT item, SUM(price) as total_price FROM Table GROUP BY item;`

| item    | total_price |
| ---     | ---         |
| cookie  | 3.50        |
| cupcake | 4.50        |
| brownie | 10.50       |

[Here's a diagram of how this works](https://github.com/jeremyraby/courseNotes/blob/main/sql/groupBy.jpg)

## WHERE vs HAVING

`WHERE` & `HAVING` clauses both filter data, but differ in the specific data they filter. 

| WHERE | HAVING |
| ---   | ---    |
| rows | groups of rows |
|         | aggregate functions  (SUM, COUNT, AVG) |

## Selecting records in the middle of a dataset

This can be weird, but ChatGPT explains that this is useful for displaying only a certain number of records per page, like when you're shopping online and the web app only displays 10 items per page (called "pagination"). You use the `OFFSET` clause (usually in conjunction with `LIMIT`) to display records 10 - 20 on page 2:

`SELECT * FROM items ORDER BY name LIMIT 10 OFFSET 10;`

## Database Normalization

Database normalization is like organizing a messy room - you want to group similar items together and make sure you don't have duplicates. In a database, this means breaking up data into smaller tables that are related to each other. This reduces data redundancy and makes it easier to maintain data consistency. By following normalization rules, you can ensure that data is stored in the most efficient and logical way possible. This makes it easier to query and analyze data, which ultimately leads to better decision-making. A trade-off is that data get stored on multiple tables that may need to be `JOIN`ed in order to see all relevant data about that entity.

"Primary" and "foreign" keys in tables help show how tables are related. A *primary key* is a unique identifier for each row in the table. When another table includes a column with the same identifier, even if named differently, it is a *foreign key* and can be used to `JOIN` the two tables together because they share the same column data.

**Table: artists**

|id | name |
| --- | --- | --- |
| 1 | Queen|
| 2 | George Strait |

**Table: albums**

|id | name| artist|
| --- | --- | --- |
| 1 | A Night at the Opera | 1
| 2 | Troubador | 2 |
| 3 | Somewhere Down in Texas | 2 |

The albums table has both a primary key (id) and a foreign key (artist), with the foreign key connecting to the artists table. This relationship can be graphed and is called an entity relationship (ER) diagram [here's an example from SQL Murder Mystery](https://github.com/jeremyraby/courseNotes/blob/main/sql/entityRelationshipDiagram.jpg)

## Joining tables
