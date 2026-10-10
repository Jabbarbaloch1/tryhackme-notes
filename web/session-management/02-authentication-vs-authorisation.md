# Authentication vs Authorisation

**Authentication vs Authorization vs Accountability**

![image.png](Authentication%20vs%20Authorisation/image.png)

These three concepts work together with **Session Management**.

### 1. Authentication — **Who are you?**

Authentication checks the user's identity.

**Example:**

```
Username + Password
        ↓
   Server verifies
        ↓
      Login
```

➡️ It creates/establishes the user's authenticated session.

---

### 2. Authorization — **What are you allowed to do?**

After login, the server checks what the user is permitted to access or perform.

**Example:**

| User | Action | Allowed? |
| --- | --- | --- |
| Normal User | View profile | ✅ |
| Normal User | Delete another user | ❌ |
| Admin | Delete user | ✅ |

➡️ Authorization is checked using the **session/user associated with the request**.

---

### 3. Accountability — **What did you do?**

Accountability means **recording user actions**.

The application should log:

- Which user performed the action
- Which session was used
- What action was performed
- When it happened

**Example:**

```
User: Abdul
Session: S12345
Action: Changed password
Time: 10:30 AM
```

If a security incident happens, these logs help investigators understand **what happened and who/which session performed the actions**.

---

# IAAA + Session Management

**IAAA** means:

```
Identification
      ↓
Authentication
      ↓
Authorization
      ↓
Accountability
      ↓
Session Management
```

### Easy way to remember:

- **Identification** → Who do you claim to be?
- **Authentication** → Prove who you are.
- **Authorization** → What can you do?
- **Accountability** → What did you do?

### How it connects to sessions

```
Login
  ↓
Authentication
  ↓
Session Created
  ↓
User sends request + Session ID
  ↓
Authorization checks permission
  ↓
Action performed
  ↓
Request + Session recorded in logs
  ↓
Accountability
```

### ⭐ One-line exam answer

> **Authentication verifies identity, authorization checks permissions, and accountability records user actions. Session management connects these processes by securely tracking the user's session.**
>