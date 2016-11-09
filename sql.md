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
