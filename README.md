## GLOSSARY
**Structured Query Language (SQL):**<br>
- a programming language designed to manage data stored in relational databases<br>
- operates through simple, declarative statements to keep data accurate and secure, and help maintain the integrity of databases, regardless of size<br>

**Relational Database:**<br>
- a dabatase that organizes information into one or more tables<br>

**Table:**<br>
- a collection of data organized into rows and columns<br>
- sometimes referred to as _relations_<br>

**Column:**<br>
- a set of data values of a particular type<br>

**Row:**<br>
- a single record in a table<br>

**Statement:**<br>
- text that the database recognizes as a valid command<br>
- always ends in a semicolon (;) <br>

**Clauses:**<br>
- perform specific tasks in SQL <br>
- written in capital letters<br>

**Parameter:**<br>
- a list of columns, data types, or values that are passed to a clause as an argument<br>

**Constraints:**<br>
- add information about how a column can be used are invoked after specifying the data type for a column <br>
- can be used to tell the database to reject inserted data that does not adhere to a certain restriction <br>



## MANIPULATION
1. **CREATE** <br>
- to create a new table in the database <br>
``` sql
CREATE TABLE celebs (
	id INTEGER,
	name TEXT,
	age INTEGER
);
```

2. **INSERT** <br>
- to insert a new row into a table <br>
- (id, name, age) is a parameter identifying the columns that data will be inserted into <br>
```sql
INSERT INTO celebs (id, name, age)
VALUES (1, 'Justin Bieber', 29);
```

3. **SELECT** <br>
- to fetch data from a database <br>
- * is a special wildcard character that allows to select every column in a table without having to name each one individually <br>
- always return a new table called _result set_ <br>
```sql
SELECT * FROM celebs;
```

4. **ALTER** <br>
- to add a new column to a table <br>
- can be used to add columns to a table <br>
```sql
ALTER TABLE celebs
ADD COLUMN twitter_handle TEXT;
```

5. **UPDATE** <br>
- to edit a row in a table <br>
```sql
UPDATE celebs
SET twitter_handle = '@taylorswift13'
WHERE id = 4;
```

6. **WHERE** <br>
- a clause that idicates which row(s) to update with the new column value <br>

7. **DELETE** <br>
- to delete one or more rows from a table <br>
```sql
DELETE FROM celebs
WHERE twitter_handle IS NULL;
```


## CONSTRAINTS
a. **PRIMARY KEY**<br>
- can be used to uniquely identify the row <br>
- attempts to insert a row with an identical value to a row already in the table will result in a _constraint violation_ which will not allow inserting the new row <br>

b. **UNIQUE**<br>
- columns have a different value for every row <br>
- similar to PRIMARY KEY except a table can have many different UNIQUE columns <br>

c. **NOT NULL**<br>
- columns must have a value <br>

d. **DEFAULT** <br>
- columns take an additional argument that will be the assumed value for an inserted row if the new row does not specify a value for that olumn <br>

