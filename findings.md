# Findings Register

This file is a structured register for the observations documented in the Week 02 assessment.

## F-01 — Web Technology Information Exposed

**Severity:** Medium

**Evidence:** `[Insert actual evidence]`

**Observation:** Technology fingerprinting may identify CMS, plugins, frameworks or server components.

**Impact:** Exposed technology information may assist subsequent authorized security assessment.

**Recommendation:** Review unnecessary public disclosure and maintain software updates.

---

## F-02 — Server/IP Information Identifiable

**Severity:** Low

**Evidence:** `[Insert actual evidence]`

**Observation:** DNS resolution may identify the address serving the application.

**Impact:** Provides infrastructure information useful for external mapping.

**Recommendation:** Review whether the information is operationally necessary and ensure the service is securely configured.

---

## F-03 — HTTP Technical Information Exposed

**Severity:** Low

**Evidence:** `[Insert actual evidence]`

**Observation:** HTTP response headers may reveal implementation details.

**Impact:** May assist technology fingerprinting and subsequent authorized enumeration.

**Recommendation:** Minimize unnecessary technical disclosure.

---

## F-04 — WAF Technology Identifiable

**Severity:** Low

**Evidence:** `[Insert actual evidence]`

**Observation:** External behavior may identify the presence or vendor of a WAF.

**Impact:** Provides information about the defensive architecture.

**Recommendation:** Keep the WAF maintained, monitored and appropriately configured.

---

## F-05 — DNS Infrastructure Information Exposed

**Severity:** Medium

**Evidence:** `[Insert actual evidence]`

**Observation:** Public DNS records may reveal name servers, mail systems and service information.

**Impact:** Can contribute to an external infrastructure profile.

**Recommendation:** Audit DNS records and remove obsolete or unnecessary entries.

---

## F-06 — Multiple Live Hosts Visible on Authorized LAN

**Severity:** Medium

**Evidence:** `[Insert actual Zenmap evidence]`

**Observation:** Host discovery identifies active devices on the authorized local network.

**Impact:** Unknown or unauthorized devices could indicate asset-management or network-control issues.

**Recommendation:** Maintain an accurate asset inventory and investigate unexpected devices.
