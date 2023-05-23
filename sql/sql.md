# SQL Basics

## Basic Elements of a Query

| Purpose                 | Clause   | Example |
| ---                     | ---      | ---     |
| To choose columns       | SELECT   | name, MIN(year) AS oldest_work_from |
| To choose a table       | FROM     | artworks |
| To join a table         | JOIN     | artists |
|                         | ON       | artworks.artist_id = artists.id |
| To filter records       | WHERE    | title != 'The Mona Lisa' |
| To group records        | GROUP BY | name |
| To filter groups        | HAVING   | MIN(year) < 1700 |
| To sort output          | ORDER BY | MIN(year) |
| Show only a few records | LIMIT    | LIMIT 1 |
| Skip x num of records   | OFFSET   | OFFSET 2 |

## Order of Operations

SQL queries have an order of operations similar to algebraic equations. The order may change depending on which clauses are used in the query, but generally speaking the order is:

1. FROM
2. JOIN
3. WHERE
4. GROUP BY
5. HAVING
6. SELECT
7. ORDER BY
8. LIMIT & OFFSET

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

`SELECT item, SUM(price) as total_price FROM sales GROUP BY item;`

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

### Inner joins

Will only return rows/records common to **both** tables

`SELECT artists.name, albums.name FROM artists INNER JOIN albums ON artists.name = albums.artist`

### Outer joins

Will return rows/records from both tables, but will show **all* rows/records in one table, regardless if a match exists in the other table.

- LEFT/RIGHT/FULL JOIN all have similar syntax as INNER JOINs
  - LEFT will show all rows from the left table regardless if there's a matching row in the right table

## Making Changes to Tables

### Inserting new data

- If you know all values for each column to enter:

`INSERT INTO table VALUES (val1, val2)`

- If you're only going to enter values for specific columns:

`INSERT INTO table (col1, col2) VALUES (val1, val2)`

### Updating data in a table

`UPDATE table SET column = newValue WHERE condition`

> Not including the WHERE clause will apply the change to **every** row

### Deleting data

- Will only delete rows

`DELETE FROM table WHERE condition`

### Creating new tables

`CREATE TABLE tableName(column DataType TableConstraint DEFAULT DefaultValue)`

- Comma separate multiple columns
- `TableConstraint` and `DefaultValue` are *optional*
- `CREATE TABLE IF NOT EXISTS` can be used to prevent errors and duplicate tables

#### Data Types

| Data Type | Description |
| ---       | ---         |
| INTEGER, BOOLEAN | The integer datatypes can store whole integer values like the count of a number or an age. In some implementations, the boolean value is just represented as an integer value of just 0 or 1 |
| FLOAT, DOUBLE, REAL | The floating point datatypes can store more precise numerical data like measurements or fractional values. Different types can be used depending on the floating point precision required for that value |
| CHARACTER(num_chars), VARCHAR(num_chars), TEXT | The text based datatypes can store strings and text in all sorts of locales. The distinction between the various types generally amount to underlaying efficiency of the database when working with these columns |
| | Both the CHARACTER and VARCHAR (variable character) types are specified with the max number of characters that they can store (longer values may be truncated), so can be more efficient to store and query with big tables. |
| DATE, DATETIME | SQL can also store date and time stamps to keep track of time series and event data. They can be tricky to work with especially when manipulating data across timezones |

#### Table Constraints

| Constraint | Description |
| ---        | ---         |
| PRIMARY KEY | This means that the values in this column are unique, and each value can be used to identify a single row in this table. |
| AUTOINCREMENT | For integer values, this means that the value is automatically filled in and incremented with each row insertion. Not supported in all databases. |
| UNIQUE | This means that the values in this column have to be unique, so you can't insert another row with the same value in this column as another row in the table. Differs from the `PRIMARY KEY` in that it doesn't have to be a key for a row in the table. |
| NOT NULL | This means that the inserted value can not be `NULL`. |
| CHECK (expression) | This allows you to run a more complex expression to test whether the values inserted are valid. For example, you can check that values are positive, or greater than a specific size, or start with a certain prefix, etc. |
| FOREIGN KEY | This is a consistency check which ensures that each value in this column corresponds to another value in a column in another table. |
| | For example, if there are two tables, one listing all Employees by ID, and another listing their payroll information, the `FOREIGN KEY` can ensure that every row in the payroll table corresponds to a valid employee in the master Employee list. |

`CREATE TABLE movies (
    id INTEGER PRIMARY KEY,
    title TEXT,
    director TEXT,
    year INTEGER, 
    length_minutes INTEGER
);`

### Making changes to table columns

All of this will begin with the `ALTER TABLE` clause

#### Adding columns

`ALTER TABLE table ADD column DataType TableConstraint DEFAULT DefaultValue`

#### Deleting columns

`ALTER TABLE table DROP column`

#### Renaming tables

`ALTER TABLE table RENAME TO newTable`

### Deleting Tables

`DROP TABLE table` OR `DROP TABLE IF EXISTS table`

If you have another table that is dependent on columns in table you are removing (for example, with a `FOREIGN KEY` dependency) then you will have to either update all dependent tables first to remove the dependent rows or to remove those tables entirely.
