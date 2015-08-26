<!-- Find all rows that have an ingredient name of Brussels sprouts. -->
<!-- SQL Query: -->
```sql
CREATE INDEX ON ingredients(name);
EXPLAIN ANALYSE SELECT * FROM ingredients WHERE name = 'Brussels sprouts';
```
<!-- Before: -->![alt](http://i.imgur.com/L6QIo3F.png)
<!-- After: -->![alt](http://i.imgur.com/KmljC0J.png)

<!-- Calculate the total count of rows of ingredients with a name of Brussels sprouts. -->
<!-- SQL Query: -->
```sql
CREATE INDEX ON ingredients(name);
EXPLAIN ANALYSE SELECT count(name) FROM ingredients WHERE name = 'Brussels sprouts';
```
<!-- Before: -->![alt](http://i.imgur.com/jGfNWwB.png)
<!-- After: -->![alt](http://i.imgur.com/UhgGaxs.png)


<!-- Find all Brussels sprouts ingredients having a unit type of gallon(s). -->
<!-- SQL Query: -->
```sql
CREATE INDEX ON ingredients(name);
CREATE INDEX ON ingredients(unit);
EXPLAIN ANALYSE SELECT * FROM ingredients WHERE unit = 'gallon(s)' AND name = 'Brussels sprouts';
```
<!-- Before: -->![alt](http://i.imgur.com/uv5CeW8.png)
<!-- After: -->![alt](http://i.imgur.com/bw28QLO.png)


<!-- Find all rows that have a unit type of gallon(s), a name of Brussels sprouts or has the letter j in it. -->
<!-- SQL Query: -->
```sql
CREATE INDEX ON ingredients(name);
CREATE INDEX ON ingredients(unit);
EXPLAIN ANALYSE SELECT * FROM ingredients WHERE unit = 'gallon(s)' AND name = 'Brussels sprouts' AND name LIKE '%j%';
```
<!-- Before: -->![alt](http://i.imgur.com/oY1U1l9.png)
<!-- After: -->![alt](http://i.imgur.com/is2rnma.png)
