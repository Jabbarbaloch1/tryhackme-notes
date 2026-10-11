# OTP-Leakage

**What is it?**

- A bug where the **OTP (one-time password)** code leaks inside the **XHR response** (data sent back by the server to the browser).
- Happens because of weak or careless coding in the **2FA** (Two-Factor Authentication) system.

**Common Causes**

| Cause | Explanation |
| --- | --- |
| Server returns OTP directly | Server should just say “success/fail” but instead sends back the actual OTP (often leftover from debugging/logging) |
| Poor security awareness | Developers focus on making the feature work, not on hiding sensitive data |
| Lack of secure coding knowledge | Developers may not know the risk of exposing OTP in responses |
| Debug info left in production | Testing/debug details are not removed before the app goes live |