# Cookie Vs Token

Cookies vs Tokens

![image.png](Cookie%20Vs%20Token/image.png)

![image.png](Cookie%20Vs%20Token/image%201.png)

There are **two common ways** to manage a user's session:

1. **Cookie-based sessions**
2. **Token-based sessions**

---

## 1. Cookie-Based Session

The server sends a cookie to the browser:

```
Set-Cookie: session=12345;
```

The browser stores it and **automatically sends it** with requests to the correct website.

### Simple flow

```
Login
 ↓
Server creates session
 ↓
Set-Cookie: session=12345
 ↓
Browser stores cookie
 ↓
Browser automatically sends cookie
 ↓
Server identifies user
```

### Important Cookie Attributes

| Attribute | Purpose |
| --- | --- |
| **Secure** | Send cookie only over HTTPS |
| **HttpOnly** | JavaScript cannot read the cookie |
| **Expires** | Defines when cookie expires |
| **SameSite** | Controls cross-site sending; helps protect against CSRF |

### Main risk

Because the browser automatically sends cookies, they can be involved in **CSRF attacks**.

---

# 2. Token-Based Session

Instead of the browser automatically managing a cookie, **JavaScript manages the token**.

After login:

```
Login
 ↓
Server gives Token
 ↓
JavaScript stores Token
 ↓
JavaScript adds Token to requests
 ↓
Server verifies Token
```

A common example is **JWT**.

The token is commonly sent like:

```
Authorization: Bearer <token>
```

The token may be stored in browser storage such as **LocalStorage**.

### Main risk

JavaScript has more control over the token, so if malicious JavaScript runs in the application, such as through an **XSS vulnerability**, the token may be exposed.

---

# Cookie vs Token

| Cookie | Token |
| --- | --- |
| Browser automatically sends it | JavaScript sends it |
| Has built-in cookie security attributes | No automatic cookie protections |
| Can be vulnerable to CSRF | Generally not automatically sent cross-site, reducing traditional CSRF risk |
| Good for traditional web applications | Useful for APIs and distributed applications |
| Example: `session=12345` | Example: `Authorization: Bearer <JWT>` |

### ⭐ Easy memory trick

**Cookie = Browser manages it**

**Token = JavaScript manages it**

### One-line exam answer

> **Cookie-based sessions use browser-managed cookies, while token-based sessions use tokens that client-side code attaches to requests, commonly through the Authorization header.**
>