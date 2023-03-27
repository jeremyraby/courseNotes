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
