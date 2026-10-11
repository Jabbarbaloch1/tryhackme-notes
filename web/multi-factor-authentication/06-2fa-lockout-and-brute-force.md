# 2FA Lockout & Automated Brute-Force

**The Problem**

- Some apps **log you out** completely if you fail the 2FA (OTP) step.
- This is done on purpose, as a security measure.

**Why apps do this**

| Reason | Explanation |
| --- | --- |
| Session Invalidation | Session is destroyed after a failed OTP, forcing a fresh login |
| Rate-Limiting / Lockout | Too many failed attempts → user is blocked and sent back to login |
| Security Redirection | Multiple failures → app forces re-login to confirm it’s the real user |

**Why Automation Helps Attackers**

| Benefit | Why it matters |
| --- | --- |
| Speed | Logging in manually each time is slow; a script is fast |
| Consistency | No human mistakes, always repeats the same steps correctly |
| Auto-recovery | If logged out, script logs back in by itself and keeps trying |
| Customization | Can change IP, user-agent, timing — more flexible than tools like Burp/ZAP |

**Exploitation (Practical Lab)**

- Target: `http://mfa.thm/labs/third`
- The app logs you out after each failed OTP.
- The OTP is a 4-digit PIN, but here it’s limited to range **1250–1350** (normally it would be 0000–9999) to save brute-force time.

php

```php
function generateToken() {    $token = strval(rand(1250, 1350));    $_SESSION['token'] = $token;    return 'success';}
```

**Key points**

- Apps that lock you out after failed OTP attempts are trying to stop brute-forcing — but automation can bypass this by auto-relogging.
- A weak/small OTP range (like 1250–1350) makes brute-forcing realistic and fast.
- The real vulnerability = predictable/small OTP + ability to keep retrying via automation.