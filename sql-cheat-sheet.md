## SQL Cheat Sheet

### Data Types

Here are some commonly used SQL data types:

- `INT`: Integer values.
- `VARCHAR(n)`: Variable-length character string with a maximum length of `n`.
- `CHAR(n)`: Fixed-length character string with a length of `n`.
- `DATE`: Date value in the format 'YYYY-MM-DD'.
- `DECIMAL(p, s)`: Fixed-point decimal number with `p` total digits and `s` digits after the decimal point.
- `BOOLEAN`: Boolean value (`TRUE` or `FALSE`).
- `BLOB`: Binary Large Object for storing large binary data.
- `TEXT`: Variable-length text data.

### Creating/Dropping Databases

To create a database, use the `CREATE DATABASE` statement:

```sql
CREATE DATABASE database_name;
```

To drop (delete) a database, use the DROP DATABASE statement:

```sql
DROP DATABASE database_name;
```

### Creating Tables

To create a table, use the CREATE TABLE statement along with column definitions and data types:

```sql
CREATE TABLE table_name (
  column1 datatype,
  column2 datatype,
  ...
);
```

### Inserting Data

To insert data into a table, use the INSERT INTO statement:

```sql
INSERT INTO table_name (column1, column2, ...)
VALUES (value1, value2, ...);
```

### Updating Data

To update data in a table, use the UPDATE statement:

```sql
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;
```

### Deleting Data

To delete data from a table, use the DELETE FROM statement:

```sql
DELETE FROM table_name WHERE condition;
```

### Primary Key

To specify a primary key for a table, use the PRIMARY KEY constraint:

```sql
CREATE TABLE table_name (
  column1 datatype,
  column2 datatype,
  ...
  PRIMARY KEY (column1)
);
```

### Foreign Key

To specify a foreign key constraint between two tables, use the FOREIGN KEY constraint:

```sql
CREATE TABLE table1 (
  column1 datatype PRIMARY KEY,
  ...
);

CREATE TABLE table2 (
  column1 datatype,
  ...
  FOREIGN KEY (column1) REFERENCES table1(column1)
);
```

### Dropping Tables

To drop (delete) a table, use the DROP TABLE statement:

```sql
DROP TABLE table_name;
```
