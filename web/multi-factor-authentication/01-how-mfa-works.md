# How MFA WORK

## 1. What is MFA?

MFA (Multi-Factor Authentication) is a security method that requires two or more verification factors to confirm a user's identity.

It provides extra protection to user accounts, making it harder for attackers to gain access.

Example:

1. Enter your password.
2. Enter a code from your authenticator app.
3. Access your account.

Even if an attacker knows your password, they may not be able to log in without the second factor.

## 2. MFA vs 2FA

| MFA | 2FA |
| --- | --- |
| Requires 2 or more factors. | Requires exactly 2 factors. |
| Includes 2FA. | Is a type of MFA. |
| Example: Password + fingerprint + security key. | Example: Password + OTP. |

Remember: All 2FA is MFA, but not all MFA is 2FA.

## 3. Five Types of Authentication Factors

[Login screen on a laptop isolated on white](https://images.openai.com/static-rsc-4/b5zquxa_poht5veWnz9qjgjbTsTjQO2cY29ee7hnC_LzMxVLWe9iGtTXMSRtMV_dKF4OuhYQVeyYxcqXiJrfaAAYQJHlz2EuBv3K5YxpMfWeA7yAmNvWHwhWqxAmDzgOUp7DutMlUahzeNo7kGTpiJK71bwb1pVLXdegJL-minJ_Qu7Gv35jhroGpE8TxuPu?purpose=inline)

#### 1. Something You Know

Knowledge

Information you remember.

- Password
- PIN
- Security question

Example: Entering your password.

[Xác thực 2 bước (2FA) là gì? Tìm hiểu chi tiết - Thegioididong.com](https://images.openai.com/static-rsc-4/qVVrGM1d_NAObBdA8aF0JyhSlOOfmR4cbX1G-oC2GIabLg9IAlScMu05gmWCjG1e3LXzfEPUsefvPsMKTZ5rYkQdQKUGRpP3CDEuflNCO7QnZ2Msf3wL_b4mKrnMpJEsuBLO0qfOC8OF-yctKDfJUU566ZkKb4d6enYrwvbrUuk?purpose=inline)

#### 2. Something You Have

Possession

A physical device you own or possess.

- Mobile phone
- Security key
- Smart card

Example: Entering a code from your phone.

[Como funcionam as ferramentas usadas pela PF para 'hackear' celulares? | Seguranca](https://images.openai.com/static-rsc-4/tRF13jjt50DvTvn1g8EUzNIZ9287kwEgcKFQ5lasCny2-jCwQ6Z1r_IRF4vbHdCjOEZ_u8wxB4kMSz8aQ9x126LLRmqGDHd5IEVfJbojUnFjpslk4jm1DpYcKHjXPV3EN6hIPdJGpHBj4kXE90mv8xL0r_K6QC00mVaM1-YEdvw?purpose=inline)

#### 3. Something You Are

Biometrics

Your physical characteristics.

- Fingerprint
- Face recognition
- Iris scan

Example: Unlocking your phone with your fingerprint.

Note: Biometric systems can make mistakes, so they should be used with suitable security controls.

[IP Address: Comprehensive Guide to Types, Privacy, and Management -](https://images.openai.com/static-rsc-4/86mlV2SK7dQE_v4bfFVcNTT3wqfPgRTZoh_3VRpef1Ix3xf5AFtTuqCJBRONzVWx6GUXcM8kDWDt4GBseSYrV0W6hLG_L6G8UsSKDSZYC_8Dgp-j7idzeJ5Shu_dewJA_v85DSw77rIdsLRJNT18QVGIpXczZTCwN3-HGmkf2VM?purpose=inline)

#### 4. Somewhere You Are

Location

Information about your location or network.

- IP address
- Geolocation

Example: Banking website asks for extra verification when you log in from an unfamiliar location.

[What is Biometrics? Definition, Data Types, Trends (2024)](https://images.openai.com/static-rsc-4/cpofP291Gtn7sGM2zpjM_OD_7u27bhcu-SeezxArw0mF3zNhn6i6UaMPlFDpiv2UYU-na7s9RZB9zsTYL1DehYUCyKD28zVTr2D1LoeRT1o4H13IB1DNFc9bJTz6MZK__58k3qyT1aRtCT730gCn63F2PuiNYjnyZ4L1QQbHfR4?purpose=inline)

#### 5. Something You Do

Behavior

Your actions or behavior.

- Typing pattern
- Mouse movement
- Interaction behavior

Example: A website analyzes how you type to help detect bots.

## 4. Types of 2FA

### 1. TOTP (Time-Based One-Time Password)

[TOTP: (way) more secure than SMS, but more annoying than Push](https://images.openai.com/static-rsc-4/J_34pyMZ4jw8qtHpbtxtRpxEFFiSxuwvHKXui2Eh4lGex3UNk5QNjVoDPkbonvgvimY9kZG7kIf2ifNVaCMFwI4T4e5ip4P-MoZk4L6m5rsveK0NJcMlH4lQVHmEeKVAgWN0ZDo6hmIYfCRwy2B933_NPw1zOEtL3vdJQ-aTrkA?purpose=inline)

TOTP generates a temporary code that usually changes every 30 seconds.

Examples:

- Google Authenticator
- Microsoft Authenticator
- Authy

Simple example:

1. Open your authenticator app.
2. See code `482193`.
3. Enter the code on the website.
4. The code expires and changes.

Security note: TOTP codes can still be stolen through phishing.

### 2. Push Notifications

[Identity Threat Detection & Response (ITDR) | Cisco Duo](https://images.openai.com/static-rsc-4/R3Bg6DCjg_Zjl7admDd5F4oTva8e-A-TYWYnPhYbZhbqc45rb9XtUIz4BWVz7rtnaYsoJ_iYA6ovaXytQdFPOlJeK0Yhu6xWHDRNjuMJ24PhoQGnPEngyUjy9YWyy-8jD5moxiyOdBjp5lLDgRbsZ1tLoKP_pTDg6T-aW22rQ40?purpose=inline)

The application sends a login request to your phone.

You can:

- Approve the login.
- Deny the login.

Example: Microsoft Authenticator or Duo asks you to approve a login.

MFA Fatigue Attack:

An attacker sends many login requests to a victim's phone until the victim accidentally approves one.

### 3. SMS Authentication

[Real-SIM vs. VoIP for Walmart SMS Verification](https://images.openai.com/static-rsc-4/RTxX6UU4P6gsOale_9_OG0mSBcDrFt2e-exgxm-nSwKBM-_gLrczIlnuODryqcXsgdf24tJm3-rc2p3iJEykj_VhzVrqEcHkZg5wLrzMD8IdT-_LplmvDF1DcYpA5Tycx22suSTu_V7jviSOru_RrhWVx7kyzkKzl2J9GhCTZSg?purpose=inline)

The website sends a one-time code through SMS.

Example:

1. Enter password.
2. Receive SMS: `736291`.
3. Enter code.
4. Login successfully.

Weakness: SMS codes may be exposed through phishing, phone-number takeover, or other attacks. SMS is generally weaker than phishing-resistant methods.

### 4. Hardware Tokens

[New YubiKey 5 NFC - Two-Factor authentication MFA Security Key Connect via USB A | eBay](https://images.openai.com/static-rsc-4/V2S-tXWR8KTNnKikLGnuVLj71PBYcrkkyJJ8G4WFl41jHuCk-Z6HZKiy21gR12y7pRhprjtuK-7zioX3XZgbtXpUeCBGE1_YFP1YuZ5D_CdP56kBUNBI4x02M9S_uYl8Tx2itc70hWbH9dIIlxgSy9btSV85m9JvUiTK97n1OPA?purpose=inline)

A physical security device used for authentication.

Example: YubiKey.

Some hardware tokens support one-time codes, while security keys can support phishing-resistant authentication such as FIDO2/WebAuthn.

Benefit: Security keys can provide strong protection against phishing.

## 5. Conditional Access

Conditional Access means the application changes security requirements based on the login situation.

Think of it as:

> If a condition is unusual, ask for extra security.
> 

[8 Avantages de l’authentification multifacteur (MFA) | Ping Identity](https://images.openai.com/static-rsc-4/Eq_Dk2JxARHw7fB-yAVlQSQyYx6XXDdgztcLuUzjTsbxU0_jFXw_m3hl70Yhw8AecpgC6PzFspLQ75xjk4e9tT_C1SriMpm5TKH2IZBOTuO-lfjMnrRfVWJjJ9qAbWFITxd8_2DA32cBUQEmNI_787qRW-UopGRQiKNY2iQ_m80?purpose=inline)

### Types

| Type | Simple Example |
| --- | --- |
| Location-based | New country → Ask for OTP |
| Time-based | Login after office hours → Extra verification |
| Behavioral | Unusual activity → Additional authentication |
| Device-specific | Unapproved device → Block access |

Important: Conditional Access is a security policy, not a separate authentication factor.

## 6. Global Adoption and Regulations

Organizations are increasingly using MFA to protect accounts against:

- Phishing
- Social engineering
- Password attacks

Some regulations and security frameworks may include authentication requirements.

| Framework | Area |
| --- | --- |
| GDPR | Data protection in the European Union |
| HIPAA | US healthcare information privacy and security requirements |
| PCI DSS | Payment card data security |

Important correction: These frameworks do not all impose one universal MFA requirement for every situation. Requirements depend on the applicable rules, systems, and circumstances.

## 7. Bug Bounty: What to Remember

When testing authentication in an authorized lab or VDP, understand:

| Topic | What to Learn |
| --- | --- |
| OTP | Expiry, reuse, and verification |
| MFA | Whether the second factor is properly enforced |
| Push MFA | Risks of repeated approval requests |
| SMS | Code protection and verification |
| Conditional Access | How risk-based security rules work |