# 🛡️ OSINT Reconnaissance Report — networkwalks.com

**theHarvester Email & Subdomain Enumeration**
*Authorized Educational Security Assessment · Networkwalks Program B082*

---

## Quick Facts

| | |
|---|---|
| **Pentester** | Kovilen Sookalingum |
| **Date** | August 2026 |
| **Status** | ✅ Authorized |
| **Target** | networkwalks.com |
| **Permission Secured** | Yes |
| **Tool** | theHarvester v4.11.1 |
| **Assessment Type** | Passive OSINT (no active exploitation) |

---

## ⚠️ Authorization Notice

> This assessment was carried out **only** with prior written authorization from the target organization. All activity documented here is passive, open-source information gathering — no systems were accessed, scanned intrusively, or exploited. This repository is published for educational purposes only. Unauthorized use of these techniques against systems you don't own or have permission to test is illegal in most jurisdictions.

---

# Executive Summary

Using **theHarvester**, a passive scan of `networkwalks.com` surfaced **1 public email address** and **3 subdomains** through open-source search engines and code repositories — no active probing of the target's infrastructure was required. This kind of exposure is exactly what a real attacker would find first, before ever touching the target directly.

---

## 🎯 Why This Matters

Reconnaissance is step one of almost every real-world attack chain. Before an attacker scans a single port, they usually build a picture from what's already public: staff emails, subdomains, leaked mentions in code repos, DNS metadata. theHarvester automates that first pass. Running it against your own (authorized) domain shows you exactly what that picture looks like from the outside.

---

## 🧰 Tool Setup

**Command:**
```bash
theHarvester -h
```

Before scanning, the tool's availability and options were confirmed from the Kali application menu and terminal.

📸 **Evidence:**
`screenshots/h1.jpeg` — theHarvester located in the Kali app launcher
`screenshots/h2.jpeg` — Version banner (v4.11.1) and usage/help output

![Tool Discovery](screenshots/h1.jpeg)
![Help Menu](screenshots/h2.jpeg)

---

## 🔍 The Scan

**Command:**
```bash
theHarvester -d networkwalks.com -b all
```

📸 **Evidence:**
`screenshots/h3.jpeg` — Full scan output

![Scan Results](screenshots/h3.jpeg)

**What came back:**

| Category | Result |
|---|---|
| Search hits (source 1) | 43 results |
| Search hits (source 2) | 76 results |
| GitHub code search | Performed, no additional data |
| IP addresses | None found |
| Employee names | None found |
| **Emails found** | **1** |
| **Hosts/subdomains found** | **3** |

**Email discovered:**
- `info@networkwalks.com`

**Subdomains discovered:**
- `cpanel.networkwalks.com`
- `cpcalendars.networkwalks.com`
- `tcp.networkwalks.com`

---

## 🚦 Findings at a Glance

| Risk | Finding |
|---|---|
| 🟡 Medium | `cpanel` subdomain is publicly resolvable — administrative panels are a common brute-force target |
| 🟢 Low–Medium | `cpcalendars` subdomain also exposed, same service family as cPanel |
| 🟢 Low | `info@` address is public and could be used as a phishing/social-engineering entry point |
| 🔵 Informational | `tcp` subdomain purpose unclear from OSINT alone — needs authorized follow-up to confirm intent |

---

## ✅ Recommendations

- Put `cpanel.*` and `cpcalendars.*` behind IP allow-listing, a VPN, or at minimum enforce MFA on login.
- Don't expose admin control panels to the open internet unless there's a clear business need.
- Treat the harvested `info@` address as a known phishing target — train staff accordingly.
- Confirm what `tcp.networkwalks.com` actually is; unexplained subdomains are worth chasing down.
- Repeat this kind of self-OSINT periodically — your public footprint changes over time.

---


## 👤 Author

**Kovilen Sookalingum**
Program: B082 – Networkwalks · Week 02 · August 2026
