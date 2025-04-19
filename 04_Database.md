Vector Databases RDBMS vs Spreadsheets Which is better for large datasets. Why? ACID Properties followed by SQL or NoSQL? ER Diagram was introduced in 1973. The same year C++ was launched. Databases is not only about RDBMS.

We will be connecting SQL databases through programming. We will be doing this with Python. The way in which we opened a file with code, why can't we access a database with that simplicity? The number one reason is security. In file, we can make it read only or write only. No more security can be provided to the file.

The second reason can be speed. They are extremely fast in read operations. Access speed in RDBMS is slow becaue it has to look for indices, partitions, constraints.

Read Operations are generally slower in NoSQL than SQL.

Our Mobile gets to know about the notification of a particular application through its port number. Socket Programming. Languages like Java and Python has libraries to implement this socket programming.

Connecting MySQL Database using Python:

```python

import pymysql

con = pymysql.connect(host = "localhost", port = 3306, user = "root",
                      password = "dbda", database = "mydb3")

mycursor = con.cursor()

# mycursor.execute("Create table employee(empid int, empname varchar(99), salary int)")

# print(mycursor.execute("desc employee"))
mycursor.execute("Insert into employee values(123, 'Viraj', 100000)")
#  It is pointer to the database

con.commit()

con.close()
```
Three main questions mainly asked in SQL Interview:

Why TRUNCATE is a DDL and not a DML despite the fact that it does not alter the schema? (Tricky questions on DDL and DML)
Joins
Normalisation

-----

CRUD Operations are DML.
Here, Create does not mean Creating Data but inserting Data into the table.

NoSQL Databases:

1. Key-value pair: Redis
2. Column Oriented: HBase
3. Document Oriented: MongoDB
4. Graph Based: Neo4j

Distributed Database:
Master-Slave Architecture

Clusters
Partitioning:
Vertical Partitioning
Horizontal Partition: row-wise

REST: Representational State Transfer
RestAPI: Programs that convert object state to JSON
REST Services

Difference between entities in Python and MongoDB.

No Joins in MongoDB.
How to choose between SQL and MongoDB to perform tasks?
In speed, MongoDB is good.
