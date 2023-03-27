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
