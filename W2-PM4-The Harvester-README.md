# OSINT Reconnaissance Report – networkwalks.com

**Tool Used:** theHarvester v4.11.1
**Platform:** Kali Linux (VirtualBox)
**Type of Assessment:** Passive OSINT / Open Source Reconnaissance
**Author:** [Kovilen Sookalingum]
**Date:** [20 August 2026]

---

## 1. Executive Summary

This report documents a passive OSINT reconnaissance exercise conducted against the domain **networkwalks.com** using **theHarvester**, an open-source intelligence gathering tool. The purpose of this exercise was to demonstrate the information-gathering phase of a penetration test — identifying publicly available data such as email addresses and subdomains without directly interacting with or attacking the target's infrastructure.

This is a **passive reconnaissance** exercise only. No exploitation, scanning of live systems, or unauthorized access was performed. All data was gathered from publicly indexed sources (search engines, DNS, and public repositories).

---

## 2. Objective

- Demonstrate practical use of theHarvester for OSINT.
- Identify publicly exposed email addresses associated with the target domain.
- Enumerate publicly known subdomains/hosts.
- Document findings in a professional report format suitable for a portfolio/GitHub showcase.

---

## 3. Scope

| Item | Detail |
|---|---|
| Target Domain | networkwalks.com |
| Assessment Type | Passive OSINT (no active exploitation) |
| Tool | theHarvester 4.11.1 |
| Data Sources | Search engines, DNS records, GitHub code search |
| Authorization | [State here whether this was done on a domain you own, a lab, or as a public training demo — important for any public repo] |

> ⚠️ **Note:** Always ensure you have explicit permission before running any reconnaissance or testing against a domain you do not own or control.

---

## 4. Tools & Environment

- **OS:** Kali Linux (running in VirtualBox)
- **Tool:** [theHarvester](https://github.com/laramies/theHarvester) v4.11.1 — coded by Christian Martorella (Edge-Security Research)
- **Terminal:** GHOST@GHOST session
- **Command executed:**
```bash
theHarvester -d networkwalks.com -b all
```
*(adjust this to reflect the actual flags you used, e.g. `-b` source, `-l` limit)*

### Screenshot 1 – Tool Discovery
Shows the Kali application launcher search results for "the", confirming theHarvester and related recon tools are installed and available.

`![Tool Discovery](screenshots/h1.jpeg)`

### Screenshot 2 – Help Menu / Tool Banner
Displays the theHarvester banner, version (4.11.1), author credit, and usage/help output (`-h` flag), confirming tool version and available options.

`![Help Menu](screenshots/h2.jpeg)`

---

## 5. Methodology

1. Launched Kali Linux application menu and located theHarvester.
2. Opened a terminal session and verified tool version and usage via `theHarvester -h`.
3. Executed a domain search against `networkwalks.com`.
4. Reviewed and recorded output: search result counts, emails, hosts/subdomains, and IPs.
5. Compiled findings into this report.

---

## 6. Findings

### 6.1 Search Summary

| Search Source | Results |
|---|---|
| General Search | 43 results |
| Secondary Source | 76 results |
| Github-code | Searched (0 results relevant) |

### 6.2 Emails Discovered

| Email Address |
|---|
| info@networkwalks.com |

**Total Emails Found:** 1

### 6.3 Hosts / Subdomains Discovered

| Subdomain |
|---|
| cpanel.networkwalks.com |
| cpcalendars.networkwalks.com |
| tcp.networkwalks.com |

**Total Hosts Found:** 3

### 6.4 IP Addresses Discovered

No IP addresses were disclosed through this passive search.

### 6.5 People/Employees Discovered

No individual names or employee profiles were discovered through this search.

### Screenshot 3 – theHarvester Scan Results
Full output of the scan against `networkwalks.com`, showing emails found, hosts found, and search statistics.

`![Scan Results](screenshots/h3.jpeg)`

---

## 7. Risk Analysis / Observations

| Finding | Risk Level | Notes |
|---|---|---|
| Exposed `cpanel` subdomain | Medium | cPanel login portals are common brute-force/enumeration targets if exposed publicly. Recommend restricting access by IP or VPN. |
| Exposed `cpcalendars` subdomain | Low–Medium | Related to cPanel's calendar service; same exposure considerations apply. |
| Public info@ email | Low | Generic contact addresses are expected to be public and pose minimal risk on their own, but can be used as a starting point for phishing/social engineering. |
| `tcp` subdomain | Informational | Purpose unclear from OSINT alone; would require further (authorized) investigation to determine function. |

---

## 8. Recommendations

- Restrict access to `cpanel.*` and `cpcalendars.*` subdomains to trusted IP ranges or place behind a VPN/2FA-protected gateway.
- Avoid exposing administrative interfaces (cPanel, WHM, etc.) directly to the public internet where possible.
- Monitor for email harvesting and consider using role-based/alias addresses that can be rotated if abused.
- Conduct periodic OSINT self-assessments to understand what information about the organization is publicly discoverable.

---

## 9. Conclusion

This exercise demonstrates the reconnaissance (information-gathering) phase of a typical penetration testing methodology. Using theHarvester, publicly available emails and subdomains associated with networkwalks.com were successfully identified without any active or intrusive interaction with the target's systems. This type of passive intelligence gathering is typically the first step attackers (and legitimate penetration testers) take, underscoring the importance of minimizing an organization's publicly exposed digital footprint.

---
