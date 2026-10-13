# Domain Hierarchy

# Task 2: Domain Hierarchy

The **Domain Name System (DNS)** is organized as a **hierarchical tree structure**.

It is read from **right to left**, starting from the **Root Domain** and moving through the **TLD → SLD → Subdomain**.

![image.png](Domain%20Hierarchy/image.png)

---

## 1. Root Domain

- **Symbol:** `.`
- **Position:** Top of the DNS hierarchy
- **Role:** Starting point for uncached DNS resolution queries

**Example:**

`.com.`

The final `.` represents the **Root Domain**.

---

## 2. Top-Level Domain (TLD)

The **TLD** is the rightmost part of a domain name, located directly below the Root Domain.

### gTLD — Generic Top-Level Domain

Used to describe the purpose or type of organization.

| TLD | Purpose |
| --- | --- |
| `.com` | Commercial organizations |
| `.org` | Non-profit organizations |
| `.edu` | Educational institutions |
| `.gov` | Government entities |
| `.mil` | Military entities |
| `.online` | General-purpose modern TLD |
| `.club` | Clubs or communities |
| `.website` | Websites |
| `.biz` | Business |

### ccTLD — Country Code Top-Level Domain

Used to represent a country or geographical region.

**Examples:**

- `.ca` → Canada
- `.uk` → United Kingdom
- `.pk` → Pakistan
- `.au` → Australia

---

## 3. Second-Level Domain (SLD)

The **SLD** is positioned directly to the left of the TLD.

**Examples:**

- `tryhackme.com` → `tryhackme` is the SLD
- `google.com` → `google` is the SLD

### Rules

- **Maximum length:** 63 characters
- **Allowed characters:** `a-z`, `0-9`,
- Cannot start with a hyphen
- Cannot end with a hyphen
- Cannot use consecutive hyphens

**Example:**

`tryhackme.com`

- `tryhackme` → SLD
- `.com` → TLD

---

## 4. Subdomain

A **subdomain** is placed to the left of the SLD and separated by a dot `.`.

**Example:**

`admin.tryhackme.com`

- `admin` → Subdomain
- `tryhackme` → SLD
- `.com` → TLD

### Usage

Subdomains are commonly used to organize:

- Internal services
- Servers
- Applications
- Development environments
- Specific resources

**Example:**

`jupiter.servers.tryhackme.com`

- `jupiter` → Subdomain
- `servers` → Subdomain
- `tryhackme` → SLD
- `.com` → TLD

### Limits

- Each subdomain label can be **up to 63 characters**
- The complete domain name (FQDN) can be **up to 253 characters**

---

# DNS Hierarchy Summary

| Level | Example | Character Limit | Role |
| --- | --- | --- | --- |
| **Root Domain** | `.` | 1 character | Top node of the DNS tree |
| **Top-Level Domain (TLD)** | `.com`, `.edu`, `.gov` | Variable | Entity purpose or geographic region |
| **Second-Level Domain (SLD)** | `tryhackme`, `google` | 63 characters | Registered brand or custom domain |
| **Subdomain** | `admin`, `servers` | 63 characters | Specific server, application, or resource |

---

# Example: `admin.tryhackme.com.`

Read from **right to left**:

**`.` → `.com` → `tryhackme` → `admin`**

| Part | Name |
| --- | --- |
| `.` | Root Domain |
| `.com` | TLD |
| `tryhackme` | SLD |
| `admin` | Subdomain |

[https://app.notion.com](https://app.notion.com)