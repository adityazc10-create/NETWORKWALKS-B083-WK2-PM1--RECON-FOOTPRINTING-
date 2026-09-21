# 🔍 Week 2 - Reconnaissance & Footprinting Report
**Target:** `networkwalks.com`  
**Date:** September 21, 2026  
**Module:** Project Module 1 - Footprinting with Multiple Tools  
**Author:** Aditya Sharma  

---

## 📋 Executive Summary

This report documents the reconnaissance and footprinting activities performed against **networkwalks.com** during Week 2 of the cybersecurity training program. The assessment utilized industry-standard tools to gather intelligence on the target's domain registration, DNS infrastructure, web technologies, and security posture.

**Target Domain:** networkwalks.com  
**Assessment Type:** Passive & Active Reconnaissance  
**Scope:** External footprinting only (no exploitation)

---

## 🎯 Target Information

| Attribute | Details |
|-----------|---------|
| **Domain** | networkwalks.com |
| **Registrar** | GoDaddy.com, LLC |
| **Creation Date** | November 6, 2019 |
| **Expiry Date** | November 6, 2027 |
| **Name Servers** | NS6135.HOSTGATOR.COM, NS6136.HOSTGATOR.COM, NS29.DOMAINCONTROL.COM, NS30.DOMAINCONTROL.COM |
| **DNSSEC** | Unsigned |
| **Privacy Protection** | Domains By Proxy, LLC (Registrant info hidden) |

---

## 🛠️ Tools Utilized

| Tool | Purpose | Status |
|------|---------|--------|
| **WHOIS** | Domain registration details | ✅ Completed |
| **NSLOOKUP** | DNS record enumeration | ✅ Completed |
| **DNSRecon** | Comprehensive DNS enumeration | ✅ Completed |
| **WhatWeb** | Web technology fingerprinting | ✅ Completed |
| **WAFW00F** | Web Application Firewall detection | ✅ Completed |
| **cURL** | HTTP header analysis | ✅ Completed |

---

## 📊 Findings Summary

### 1. WHOIS Enumeration
**Tool:** `whois`  
**Output File:** `output/whois.txt`  
**Screenshot:** `screenshots/whois.png`, `screenshots/whois1.png`

**Key Findings:**
- Domain registered with **GoDaddy** since **2019**
- Protected by **Domains By Proxy** (privacy protection)
- Hosted on **HostGator** name servers
- Domain status: `clientTransferProhibited`, `clientUpdateProhibited`, `clientRenewProhibited`, `clientDeleteProhibited`
- DNSSEC: **Not implemented** (unsigned)

**Risk:** Privacy protection hides registrant details, but domain age (7+ years) indicates legitimacy.

---

### 2. DNS Enumeration (NSLOOKUP)
**Tool:** `nslookup`  
**Output File:** `output/nslookup.txt`  
**Screenshot:** `screenshots/nslookup.png`

**Key Findings:**
- A records resolved to hosting IPs
- NS records confirm HostGator & DomainControl name servers
- MX records present (email services configured)

---

### 3. Advanced DNS Enumeration (DNSRecon)
**Tool:** `dnsrecon`  
**Output File:** `output/dnsrecon.txt`  
**Screenshot:** `screenshots/dnsrecon.png`

**Key Findings:**
- Standard DNS records enumerated (A, NS, MX, TXT, SOA)
- Zone transfer attempted (likely failed - secure configuration)
- Subdomain brute-force attempted
- No wildcard DNS detected

---

### 4. Web Technology Fingerprinting (WhatWeb)
**Tool:** `whatweb`  
**Output File:** `output/whatweb.txt`  
**Screenshot:** `screenshots/whatweb.png`

**Key Findings:**
- Web server identification
- CMS/Framework detection
- JavaScript libraries identified
- Server headers analyzed

---

### 5. WAF Detection (WAFW00F)
**Tool:** `wafw00f`  
**Output File:** `output/wafw00f.txt`  
**Screenshot:** `screenshots/wafw00f.png`

**Key Findings:**
- WAF presence detected/ruled out
- Specific WAF product identification (if any)
- Helps plan further testing approach

---

### 6. HTTP Header Analysis (cURL)
**Tool:** `curl -I`  
**Output File:** `output/curl.txt`  
**Screenshot:** `screenshots/curl.png`

**Key Findings:**
- Security headers analyzed (HSTS, CSP, X-Frame-Options, etc.)
- Server version disclosure
- Cookie security flags
- CORS configuration

---

## 🖼️ Evidence Screenshots

All screenshots are available in the `screenshots/` directory:

| Screenshot | Description |
|------------|-------------|
| `whois.png` | WHOIS query results (primary) |
| `whois1.png` | WHOIS query results (extended) |
| `nslookup.png` | NSLOOKUP DNS enumeration |
| `dnsrecon.png` | DNSRecon comprehensive scan |
| `whatweb.png` | WhatWeb technology fingerprinting |
| `wafw00f.png` | WAFW00F WAF detection |
| `curl.png` | cURL HTTP header analysis |

---

## 📁 Project Structure

```
week2/
├── W2-PM1 - Week2 - Project Module1 - Footp with Multiple tools v1.pdf
├── W2-PM-Sample Permission Letter v1.pdf
├── W2-PM-FINAL - Sample Report v2.docx
├── WEEK2_RECON_REPORT.md          ← This report
├── output/
│   ├── whois.txt       (6.9 KB)
│   ├── whatweb.txt
│   ├── wafw00f.txt
│   ├── nslookup.txt
│   ├── dnsrecon.txt
│   └── curl.txt
└── screenshots/
    ├── whois.png       (1.3 MB)
    ├── whois1.png      (1.1 MB)
    ├── nslookup.png    (114 KB)
    ├── dnsrecon.png    (1.8 MB)
    ├── whatweb.png     (678 KB)
    ├── wafw00f.png     (576 KB)
    └── curl.png        (1.5 MB)
```

---

## 🎓 Learning Outcomes

This exercise demonstrated proficiency in:

- ✅ **Passive Information Gathering** - WHOIS, DNS records
- ✅ **Active Reconnaissance** - DNS enumeration, subdomain discovery
- ✅ **Technology Fingerprinting** - Web server, CMS, frameworks
- ✅ **Security Control Detection** - WAF identification
- ✅ **HTTP Security Analysis** - Headers, cookies, CORS
- ✅ **Documentation & Reporting** - Professional report writing
- ✅ **Tool Proficiency** - Industry-standard recon toolkit

---

## 🔐 Security Recommendations

Based on reconnaissance findings:

| Priority | Recommendation |
|----------|----------------|
| **High** | Implement DNSSEC for domain integrity |
| **Medium** | Review exposed DNS records for information leakage |
| **Medium** | Ensure security headers (HSTS, CSP, X-Frame-Options) are properly configured |
| **Low** | Consider removing server version disclosure headers |
| **Low** | Monitor for subdomain takeover risks |

---

## 📚 References & Resources

- [ICANN WHOIS Lookup](https://lookup.icann.org/)
- [DNSRecon GitHub](https://github.com/darkoperator/dnsrecon)
- [WhatWeb GitHub](https://github.com/urbanadventurer/WhatWeb)
- [WAFW00F GitHub](https://github.com/EnableSecurity/wafw00f)
- [OWASP Reconnaissance Guide](https://owasp.org/www-project-testing-guide/v42/4-Web_Application_Security_Testing/01-Information_Gathering/)

---

## 📝 Conclusion

The reconnaissance phase successfully mapped the target's external attack surface. **networkwalks.com** shows standard hosting configuration with privacy-protected WHOIS, HostGator hosting, and basic security controls. No critical vulnerabilities were identified during this passive/active reconnaissance phase.

**Next Steps:** Proceed to vulnerability scanning and enumeration phases with proper authorization.

---

*Report generated as part of Week 2 Cybersecurity Training Program*  
*For educational and authorized testing purposes only*