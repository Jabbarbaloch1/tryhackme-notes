# Intro

**SQL Injection (SQLi)** 

**What is it?**

- An attack on a website’s database.
- The attacker sends bad code through an input box (like login or search).
- The database runs that code by mistake.

**Why does it happen?**

- The website does not check user input properly.
- The input goes straight into the database query.

**What can an attacker do?**

| Attack | Result |
| --- | --- |
| Steal data | Get private and customer information |
| Delete data | Remove important records |
| Change data | Edit or damage records |
| Bypass login | Enter private or customer areas without permission |

**Key points**

- It is one of the oldest web vulnerabilities.
- It can also be one of the most damaging.

**How to prevent it (quick tip)**

- Always validate user input.
- Use parameterized queries (prepared statements).