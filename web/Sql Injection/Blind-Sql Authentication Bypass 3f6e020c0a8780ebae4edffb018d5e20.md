# Blind-Sql Authentication Bypass

**What is Blind SQLi?**

- Different from In-Band SQLi — here you **can’t see** the attack results on screen.
- Error messages are turned off, but the injection **still works**.
- Even a tiny bit of feedback (like true/false) is enough to steal a whole database.

**Authentication Bypass**

- A simple type of Blind SQLi.
- Goal: **skip the login**, not steal data.
- The app asks the database: “Is there a user with this exact username and password?”
- Database replies **yes** or **no** (true/false).
- Based on that, the app lets you in or not.
- So the attacker doesn’t need a real username/password — just a query that always says **true**.

**Practical Example**

| Step | Detail |
| --- | --- |
| Normal query | `select * from users where username='%username%' and password='%password%' LIMIT 1;` |
| Payload (enter in password field) | `' OR 1=1;--` |
| Resulting query | `select * from users where username='' and password='' OR 1=1;` |

**Why it works**

- `1=1` is always **true**.
- `OR` means if **any part** is true, the whole thing is true.
- So the query always returns true → database says “match found” → login is bypassed.

**Key points**

- Blind SQLi = no visible error, but still exploitable using true/false logic.
- Authentication bypass = trick the login into always getting a “yes.”
- `' OR 1=1;--` is the classic bypass payload. `-` comments out the rest of the query (like the extra quote).