# 🔍 Week 2 - Reconnaissance & Footprinting Project

> **Target:** `networkwalks.com` | **Module:** Project Module 1 - Footprinting with Multiple Tools | **Status:** ✅ Complete

## 📋 Overview

This repository contains the complete deliverables for Week 2 Reconnaissance & Footprinting assessment. The project demonstrates practical application of industry-standard reconnaissance tools to map the external attack surface of a target domain.

## 🎯 Target Profile

| Attribute | Value |
|-----------|-------|
| **Domain** | `networkwalks.com` |
| **Registrar** | GoDaddy.com, LLC |
| **Hosting** | HostGator (NS6135/NS6136) + DomainControl (NS29/NS30) |
| **Domain Age** | 7+ years (Created: Nov 6, 2019) |
| **Privacy** | Protected via Domains By Proxy |
| **DNSSEC** | Not Implemented |

## 🛠️ Tool Arsenal

| Tool | Category | Purpose | Output |
|------|----------|---------|--------|
| `whois` | Passive Recon | Domain registration intelligence | `output/whois.txt` |
| `nslookup` | DNS Enum | Basic DNS record querying | `output/nslookup.txt` |
| `dnsrecon` | DNS Enum | Comprehensive DNS enumeration | `output/dnsrecon.txt` |
| `whatweb` | Fingerprinting | Web technology identification | `output/whatweb.txt` |
| `wafw00f` | Defense Detection | WAF identification | `output/wafw00f.txt` |
| `curl` | Header Analysis | HTTP security header audit | `output/curl.txt` |

## 📁 Repository Structure

```
week2-recon-project/
├── README.md                      # This file
├── WEEK2_RECON_REPORT.md          # Full technical report
├── LINKEDIN_POST_CONTENT.md       # Social media content templates
├── output/                        # Raw tool outputs
│   ├── whois.txt
│   ├── whatweb.txt
│   ├── wafw00f.txt
│   ├── nslookup.txt
│   ├── dnsrecon.txt
│   └── curl.txt
└── screenshots/                   # Visual evidence
    ├── whois.png
    ├── whois1.png
    ├── nslookup.png
    ├── dnsrecon.png
    ├── whatweb.png
    ├── wafw00f.png
    └── curl.png
```

## 🚀 Quick Start

### View the Report
```bash
cat WEEK2_RECON_REPORT.md
```

### Run the Tools Yourself
```bash
# WHOIS
whois networkwalks.com

# DNS Enumeration
nslookup networkwalks.com
dnsrecon -d networkwalks.com

# Technology Fingerprinting
whatweb networkwalks.com

# WAF Detection
wafw00f networkwalks.com

# Header Analysis
curl -I https://networkwalks.com
```

## 📊 Key Findings Summary

### ✅ Security Posture: **Adequate**
- Domain privacy protection enabled
- Domain status locks active (transfer/update/renew/delete prohibited)
- No critical information leakage detected
- Standard hosting configuration

### ⚠️ Areas for Improvement
- **DNSSEC not implemented** - Domain integrity not cryptographically verified
- **Security headers** - Review HSTS, CSP, X-Frame-Options implementation
- **Server disclosure** - Minimize version information in headers

### 🎯 Attack Surface Mapped
- ✅ Domain registration details
- ✅ DNS infrastructure (NS, A, MX, TXT records)
- ✅ Subdomain enumeration attempted
- ✅ Web technology stack
- ✅ WAF presence/absence
- ✅ HTTP security configuration

## 📚 Skills Demonstrated

- **Passive Information Gathering** - WHOIS, public DNS records
- **Active Reconnaissance** - DNS enumeration, zone transfer testing
- **Technology Fingerprinting** - Web server, CMS, frameworks, libraries
- **Security Control Detection** - WAF identification
- **HTTP Security Analysis** - Headers, cookies, CORS, CSP
- **Professional Documentation** - Structured reporting with evidence
- **Tool Proficiency** - 6 industry-standard reconnaissance tools

## 🔐 Authorization & Ethics

> ⚠️ **IMPORTANT:** This assessment was conducted for **educational purposes** as part of a structured cybersecurity training program. All testing was limited to:
> - Passive information gathering (public records)
> - Standard DNS queries (publicly accessible)
> - Unauthenticated web requests (public endpoints)
> - No exploitation, no unauthorized access, no data exfiltration

**Always obtain written authorization before testing any target.**

## 📖 Learning Resources

- [DNSRecon Documentation](https://github.com/darkoperator/dnsrecon)
- [WhatWeb Documentation](https://github.com/urbanadventurer/WhatWeb)
- [WAFW00F Documentation](https://github.com/EnableSecurity/wafw00f)
- [OWASP Information Gathering Guide](https://owasp.org/www-project-testing-guide/v42/4-Web_Application_Security_Testing/01-Information_Gathering/)
- [RFC 2182 - DNS Selection and Operation](https://tools.ietf.org/html/rfc2182)

## 📈 Next Steps (Week 3+)

- [ ] Vulnerability Scanning (Nessus, OpenVAS, Nuclei)
- [ ] Service Enumeration (Nmap, Masscan)
- [ ] Web Application Mapping (Burp Suite, OWASP ZAP)
- [ ] Credentialed Assessment
- [ ] Exploitation & Post-Exploitation (Authorized Only)

## 🤝 Connect

- **Author:** Aditya Sharma
- **Program:** Cybersecurity Training - Week 2
- **Date:** September 2026

---

⭐ **Star this repo if you found it useful!**  
🍴 **Fork for your own recon projects!**  
📝 **Feedback welcome via Issues!**

## 📄 License

Educational use only. See individual tool licenses for redistribution terms.

---

*Built with 🛠️ for learning | Secured with 🔐 for practice*
