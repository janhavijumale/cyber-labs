# 🔍 Search Skills – Search Engines & Advanced Operators

## 📌 Google Search Operators

| Operator | Usage | Example | Notes |
|---------|-------|---------|-------|
| `" "` | Exact match | `"passive reconnaissance"` | Returns pages with exact phrase |
| `site:` | Search within a site/domain | `site:tryhackme.com success stories` | Helpful to target specific sources |
| `-` | Exclude a keyword | `pyramids -tourism` | Use to filter out unwanted results |
| `filetype:` | Search for specific file types | `filetype:ppt cyber security` | PDF, DOC, XLS, PPT commonly used |

---

## 🌐 Specialized Search Engines

### 🔸 Shodan
- A search engine for discovering internet-connected devices.
- Can be used to find exposed IoT, webcams, routers, etc.
- Common filters:
  - `port:22` – SSH servers
  - `country:"IN"` – Results in India
  - `org:"BSNL"` – Specific ISP/org

### 🔸 Censys
- Similar to Shodan, but more data-focused and academic.
- Search by IP, domain, or certificate.
- Good for attack surface mapping and TLS certificate analysis.

### 🔸 VirusTotal
- Used to analyze suspicious files, URLs, IPs.
- Scans using multiple antivirus engines.
- Good for **file reputation checking** and **malware hunting**.

### 🔸 Have I Been Pwned
- Used to check if an email/password has been leaked in a breach.
- Important for credential exposure analysis.
- You can use their API or manually check emails.

---

## 💡 Tips
- Combine search operators to refine results:  
  `"pdf" site:gov.in filetype:pdf cyber security`
- Google dorks are powerful for OSINT, bug bounty, and recon.
- VirusTotal can be used to reverse trace malware activity via hash or IP.

