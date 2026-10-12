# What is  Database ?

**What is a database?**

- A place to store data on a computer in an organised way.
- It is controlled by a **DBMS** (Database Management System).
- DBMS has two types: **Relational** and **Non-Relational**.
- Common relational DBMSs: MySQL, Microsoft SQL Server, Access, PostgreSQL, SQLite.

**Structure**

- One DBMS can hold many databases (example: “shop”, “staff”, “accounts”).
- Each database stores data in **tables** (example: products, users, orders).
- Each table has a unique name.

**Tables**

- A table is like a grid: **columns** across the top, **rows** going down.

| Part | Meaning |
| --- | --- |
| Column (field) | Name and type of the data. Name must be unique in the table. |
| Row (record) | One line of actual data. Adding data = new row. Deleting data = row removed. |

**Columns**

- Each column has a **data type**: integer (numbers), string (text), date, or complex ones like geospatial (location).
- Data type stops wrong data going in (example: “hello world” in a date column gives an error).
- **Auto-increment:** gives each row a new number automatically (1, 2, 3...).
- **Key field:** a column that is unique for every row. Used to find one exact row in a query.

**Relational vs Non-Relational**

|  | Relational | Non-Relational (NoSQL) |
| --- | --- | --- |
| Storage | Tables, columns, rows | No tables/columns/rows |
| Structure | Fixed layout | No fixed layout, rows can differ |
| Links | Tables connect using a **primary key** | Not needed |
| Flexibility | Less | More |
| Examples | MySQL, PostgreSQL, SQL Server | MongoDB, Cassandra, ElasticSearch |

**Key points**

- Primary key = unique ID in one table, used in other tables to connect them. This is why it is called “relational”.
- This room focuses on **relational** databases.