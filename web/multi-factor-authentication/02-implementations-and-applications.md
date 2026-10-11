# Implementations and Applications

# Multi-Factor Authentication (MFA)

**Multi-Factor Authentication (MFA)** is a security control that requires users to provide **two or more different authentication factors** before accessing an account or system.

MFA helps protect against:

- Unauthorized access
- Account takeover
- Fraud
- Data breaches
- Stolen passwords

The three common authentication factors are:

- **Something You Know** → Password, PIN
- **Something You Have** → Phone, security key, authenticator app
- **Something You Are** → Fingerprint, face recognition

---

## 1. MFA in Banking

### Objective

Protects customer accounts, financial information, and transactions from:

- Account takeover
- Financial fraud
- Cyber theft
- Unauthorized transactions

### Authentication Factors

- **Something You Know:** Password or PIN
- **Something You Have:** SMS verification code or authenticator app

### Example

```
Password
   +
Authenticator Code
   ↓
Bank Account Access
```

### Security Impact

Even if an attacker steals the user's password, they may still be unable to access the account without the second authentication factor.

---

## 2. MFA in Healthcare

### Objective

Protects sensitive patient information and healthcare systems.

It can also support compliance with regulations such as **HIPAA** in the United States.

### Authentication Factors

- **Something You Have:** Physical security badge
- **Something You Are:** Fingerprint or other biometric verification

### Example

```
Security Badge
      +
Fingerprint
      ↓
Electronic Health Record Access
```

### Security Impact

MFA helps ensure that only authorized healthcare personnel can access sensitive systems such as **Electronic Health Records (EHRs)**.

---

## 3. MFA in Corporate IT

### Objective

Protects:

- Company networks
- Databases
- Cloud environments
- Internal applications
- Business data

### Authentication Factors

- **Something You Know:** Corporate username/password
- **Something You Have:** Company-issued phone or security key
- **Something You Are:** Biometric verification

### Example

```
Corporate Password
       +
Authenticator Code
       +
Biometric
       ↓
Corporate System Access
```

### Security Impact

MFA provides **defense in depth**.

If an attacker obtains an employee's password, the additional authentication factor can still prevent unauthorized access.

---

# MFA Industry Implementation Summary

| Industry | Security Goal | Primary Factors | Practical Example |
| --- | --- | --- | --- |
| **Banking** | Prevent financial fraud and account takeover | Know + Have | Password + SMS/Authenticator Code |
| **Healthcare** | Protect patient records and sensitive systems | Have + Are | Security Badge + Fingerprint |
| **Corporate IT** | Prevent unauthorized network and data access | Know + Have/Are | Password + Security Code/Biometrics |

---

# Easy Way to Remember MFA

```
Something You Know
        ↓
   Password / PIN

Something You Have
        ↓
 Phone / Security Key / Authenticator

Something You Are
        ↓
 Fingerprint / Face
```

### Key Point

> **MFA = More than one authentication factor**
> 

The important part is that the factors should come from **different categories**, not simply two passwords.