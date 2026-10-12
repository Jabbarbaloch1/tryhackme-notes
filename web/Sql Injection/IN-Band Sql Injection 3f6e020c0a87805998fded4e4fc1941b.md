# IN-Band Sql Injection

**In-Band SQL Injection –**

**What is it?**

- The easiest type of SQLi to find and use.
- “In-Band” means the **same channel** is used to attack and to get the results.
- Example: you find a weak page, attack it, and the stolen data shows up **on that same page**.

**Two main types**

| Type | How it works | Best for |
| --- | --- | --- |
| **Error-Based** | Database error messages are shown directly in the browser | Learning the database structure (can often map the whole database) |
| **Union-Based** | Uses the `UNION` operator with `SELECT` to add extra results to the page | Pulling out large amounts of data (most common method) |

**Error-Based**

- The website shows database errors on screen.
- These errors give hints about tables, columns and structure.
- Most useful for **finding out how the database is built**.

**Union-Based**

- Uses `UNION` + `SELECT` to return extra data on the page.
- Remember the UNION rules: same number of columns, similar data types, same order.
- Most common way to **extract lots of data**.

**Key points**

- In-Band = attack and results on the **same page**.
- Error-Based = learn the structure from error messages.
- Union-Based = get the data using UNION.