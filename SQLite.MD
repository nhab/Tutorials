## Create A New Database
At a shell or DOS prompt, enter: "sqlite3 test.db"

## Examples for Create,insert and select Table

` $ sqlite3 ex1 `

 ` SQLite version 3.8.5 2014-05-29 12:36:14 `
 
 ` Enter ".help" for usage hints. ` 
 
 ` sqlite> create table tbl1(one varchar(10)  primary key, two smallint, f2 text, f3 real); `
 
 ` sqlite> insert into tbl1 (one,two) values('hello!',10); `
 
` sqlite> insert into tbl1 values('goodbye', 20); `

` sqlite> select * from tbl1; `

` hello!|10 `

` goodbye|20 `

` sqlite> `

## Write to File 
`  sqlite> CREATE TABLE images(name TEXT, type TEXT, img BLOB); `
`  sqlite> INSERT INTO images(name,type,img) `
`  ...>   VALUES('icon','jpeg',readfile('icon.jpg')); `
## Read from file
` sqlite> SELECT writefile('icon.jpg',img) FROM images WHERE name='icon'; ` 

## Querying the database schema

`SELECT name FROM sqlite_master 
WHERE type IN ('table','view') AND name NOT LIKE 'sqlite_%'
ORDER BY 1`

## CSV Export
`sqlite> SELECT * FROM tab1;
sqlite> .system c:/work/dataout.csv `

