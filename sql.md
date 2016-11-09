Relational database - organizes info in tables (aka relations)  
Columns - data values of the same type  
Rows - a single record in a table  
### Creating a table
```
CREATE TABLE table_name (
    column_1 data_type,
    column_2 data_type,
    column_3 data_type
);

CREATE TABLE celebs (
    id INTEGER,
    name TEXT,
    age INTEGER
);
```

### Query the database
```
SELECT column_name FROM table_name;
SELECT column_1, column_2 FROM table_name;
SELECT DISTINCT column_name FROM table_name;
```

### Adding a row
```
INSERT INTO table_name (column_1, column_2, column_3) VALUES (value_1, 'value_2', value_3);
```

### Adding a column
```
ALTER TABLE table_name ADD column datatype;
```

### Edit rows in a table
```
UPDATE table_name
SET some_column = some_value
WHERE some_column = some_value;
```

### Remove rows from a table
```
DELETE FROM table_name WHERE some_column = some_value;
```

### Filter queries
```
SELECT * FROM table WHERE column_name operator value;
```

##### Wildcard Selects
```
SELECT column_name(s)
FROM table_name
WHERE column_name LIKE pattern;   

% - matches 0 or more missing letters
'a%' - everything that beings with 'a'
'%z' - everything that ends with 'z'
'%man%' - everything that contains 'man'
'_' - wildcard for 1 character
```

##### Filter within a range
```
SELECT column_name(s)
FROM table_name
WHERE column_name BETWEEN value_1 AND value_2;
```

##### Combining conditions
```
SELECT column_name(s)
FROM table_name
WHERE column_1 = value_1
AND column_2 = value_2;

SELECT column_name
FROM table_name
WHERE column_name = value_1
OR column_name = value_2;
```

### Ordering queries
```
SELECT column_name
FROM table_name
ORDER BY column_name ASC|DESC;
```

### Limit maximum number of rows for result set
```
SELECT column_name(s)
FROM table_name
LIMIT number;
```

### Count how many rows in a table
```
SELECT COUNT(*) FROM table_name;
```

### Arrange identical data into groups
```
SELECT COUNT(*)
FROM table_name
GROUP BY column_name;
```

### Add all values in a particular column
```
SELECT SUM(column_name) FROM table_name;
SELECT MAX(column_name) FROM table_name;        // get the maximum
```

# Multiple Tables
Primary Key - a unique identifier for each row in a given table (can't be NULL)  
Foreign Key - a column that contains the primary key for another table in db  

### Joins - Querying multiple tables
```
SELECT table_1.col_1, table_1.col_2, table_2.col_1 FROM table_1, table_2;  // cross join

// Combine rows from diff. tables if JOIN cond. is true
SELECT *
FROM table_1
JOIN table_2 ON
    table_1.foreign_key = table_2.PRIMARY_KEY;      // inner join

// Return every row of left table (table 1) in results set
SELECT *
FROM table_1
LEFT JOIN table_2 ON
    table_1.foreign_key = table_2.PRIMARY_KEY;      // outer join
```
