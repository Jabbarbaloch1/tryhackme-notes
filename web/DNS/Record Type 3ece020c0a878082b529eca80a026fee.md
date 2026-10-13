# Record Type

# Task 3: DNS Record Types

DNS is used for more than just looking up websites. Different **DNS record types** handle different networking and service requirements.

---

## 1. A Record

- **Function:** Resolves a domain name to an **IPv4 address**.
- **Example:** `104.26.10.229`

---

## 2. AAAA Record

- **Function:** Resolves a domain name to an **IPv6 address**.
- **Example:** `2606:4700:20::681a:be5`

---

## 3. CNAME Record (Canonical Name)

- **Function:** Resolves a domain name to **another domain name**, rather than directly to an IP address.
- **How It Works:** A second DNS lookup is performed for the target domain to find its actual IP address.
- **Example:**

`store.tryhackme.com` → `shops.shopify.com`

---

## 4. MX Record (Mail Exchange)

- **Function:** Points to the **mail servers** responsible for handling email for a domain.
- **Priority Flag:** Contains a priority number that tells mail servers which server to try first.
- If the primary server is unavailable, email can be sent to a backup server with a lower priority.
- **Example:** `alt1.aspmx.l.google.com`

---

## 5. TXT Record (Text)

- **Function:** Stores **text-based data** associated with a domain.

### Primary Uses

1. **Email Authentication & Anti-Spam**
    - SPF
    - DMARC
    - Helps identify authorized email-sending servers.
2. **Domain Ownership Verification**
    - Used to verify control of a domain.
    - Commonly used by third-party services and SSL/TLS certificate providers.

### Common Examples

**SSL/TLS Validation:**

`_acme-challenge.example.com TXT "token_value_here"`

**SPF Record:**

`@ TXT "v=spf1 ip4:192.0.2.0/24 include:_spf.google.com include:amazonses.com ~all"`

**DMARC Record:**

`_dmarc.example.com TXT "v=DMARC1; p=reject; rua=mailto:dmarc-reports@example.com; adkim=s; aspf=s; pct=100"`

**Service Ownership:**

`@ TXT "MS=ms12345678"`

---

# DNS Record Types Summary

| Record Type | Target / Output | Primary Purpose | Example |
| --- | --- | --- | --- |
| **A** | IPv4 Address | Direct domain-to-IPv4 mapping | `104.26.10.229` |
| **AAAA** | IPv6 Address | Direct domain-to-IPv6 mapping | `2606:4700:20::681a:be5` |
| **CNAME** | Domain Name | Points one domain to another domain | `shops.shopify.com` |
| **MX** | Mail Server + Priority | Routes incoming email and provides failover | `alt1.aspmx.l.google.com` |
| **TXT** | Arbitrary Text | Email security (SPF/DMARC) and domain validation | `"v=spf1 ... ~all"` |

---

# Easy Memory Trick

| Record | Remember |
| --- | --- |
| **A** | Domain → **IPv4** |
| **AAAA** | Domain → **IPv6** |
| **CNAME** | Domain → **Domain** |
| **MX** | Domain → **Mail Server** |
| **TXT** | Domain → **Text / Verification** |