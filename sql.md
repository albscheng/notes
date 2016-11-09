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
