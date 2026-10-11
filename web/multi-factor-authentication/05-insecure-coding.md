# Insecure-Coding

**2FA Logic Flaw / Insecure Coding – Simple Notes**

**What is the problem?**

- Sometimes an app has **bad logic or weak code** that lets you skip 2FA completely.
- You can reach the **dashboard** without ever entering the OTP.
- Caused by: bad session handling, missing access checks, or wrong logic order.

**Why this happens (the code)**

**Correct part** — this checks the OTP properly:

php

```php
function verify_2fa_code($code) {    if (!isset($_SESSION['token']))        return false;    return $code === $_SESSION['token'];}if (verify_2fa_code($_POST['code'])) {    $_SESSION['authenticated'] = true; // Set only AFTER OTP success    header('Location: ' . ROOT_DIR . '/dashboard');}
```

- `$_SESSION['authenticated']` is only set to true **after** OTP is correct. ✅ This part is safe.

**The actual bug** — found in the login step (before 2FA):

php

```php
if (authenticate($email, $password)) {    $_SESSION['authenticated'] = true; // ❌ Set too early!    $_SESSION['email'] = $_POST['email'];    header('Location: ' . ROOT_DIR . '/mfa');}
```

- Here, `$_SESSION['authenticated']` is set to **true right after password check** — before OTP is even asked.
- The dashboard only checks this **one flag**.
- So the attacker never needs to pass OTP — the flag is already true.

**The Flaw**

| Step | What should happen | What actually happens |
| --- | --- | --- |
| Username + password correct | Should only allow going to the OTP page | Already sets `authenticated = true` |
| OTP entered | Should set `authenticated = true` | Flag was already true, so OTP is pointless |

**Fix (Remediation)**

- Use **two separate session flags**:
    1. One flag after password check → only allows access to the **OTP page**.
    2. A second flag only after **OTP is verified** → allows access to the **dashboard**.
- This way, one flag alone can’t open the dashboard.

**Key points**

- Never set a “fully authenticated” session flag before 2FA is done.
- Dashboard access should check the **OTP-verified flag**, not just the login flag.
- This vulnerability type = **broken authentication logic**, not a coding typo.