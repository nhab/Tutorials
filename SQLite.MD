### Create A New Database ( or connects to existing one)
 At a shell command prompt, enter: "sqlite3 test.db"

### Examples for Create,insert and select Table
     $ sqlite3 ex1 
     SQLite version 3.8.5 2014-05-29 12:36:14 
     Enter ".help" for usage hints. 
     sqlite> create table tbl1(one varchar(10)  primary key, two smallint, f2 text, f3 real); 
     sqlite> insert into tbl1 (one,two) values('hello!',10); 
     sqlite> insert into tbl1 values('goodbye', 20); 
     sqlite> select * from tbl1; 
     hello!|10 
     goodbye|20 
### Show list of the tables
    .tables
### Show the structure of a table
    .schema table
### Add column in table
    ALTER TABLE table_name
     ADD new_column_name column_definition;
### Modify column in table
  You can not use the ALTER TABLE statement to modify a column in SQLite. 
  Instead you will need to rename the table, create a new table, and copy the data into the new table.
#### Syntax
    PRAGMA foreign_keys=off;
    BEGIN TRANSACTION;
    ALTER TABLE table1 RENAME TO _table1_old;
    CREATE TABLE table1 (
    ( column1 datatype [ NULL | NOT NULL ],
     column2 datatype [ NULL | NOT NULL ],
     ...
    );
    INSERT INTO table1 (column1, column2, ... column_n)
    SELECT column1, column2, ... column_n
    FROM _table1_old;
    COMMIT;
    PRAGMA foreign_keys=on;
### Rename the Table name
    ALTER TABLE table_name
     RENAME TO new_table_name;
### File I/O
    sqlite> CREATE TABLE images(name TEXT, type TEXT, img BLOB); 
    sqlite> INSERT INTO images(name,type,img) 
    ...>   VALUES('icon','jpeg',readfile('icon.jpg')); 
    sqlite> SELECT writefile('icon.jpg',img) FROM images WHERE name='icon'; 
### Querying the database schema
    SELECT name FROM sqlite_master 
    WHERE type IN ('table','view') AND name NOT LIKE 'sqlite_%'
    ORDER BY 1
### CSV Export /Import
    sqlite> SELECT * FROM tab1;
    sqlite> .system c:/work/dataout.csv 
    
    sqlite> .mode csv
    sqlite> .import C:/work/somedata.csv tab1

