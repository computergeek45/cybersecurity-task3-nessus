# cybersecurity-task3-nessus
Basic vulnerability scan performed using Nessus Essentials as part of a cybersecurity internship task.

# Task 3: Basic Vulnerability Scan (Cybersecurity Internship)

## Objective
To perform a vulnerability assessment on my local machine using a free industry-standard tool and identify potential risks. This task helps develop a foundational understanding of cybersecurity threats, vulnerability types, and risk mitigation techniques.

---

## Tool Used
- **Tenable Nessus Essentials**  
  A free vulnerability scanning tool that detects misconfigurations, outdated services, and security flaws on hosts and networks.

---

## Scan Details

- **Scan Name**: Localhost Scan
- **Tool**: Nessus Essentials (Web Interface)
- **Scan Type**: Basic Network Scan
- **Target**: `127.0.0.1` (localhost)
- **Status**: ✅ Completed
- **Start Time**: 4:07 PM  
- **End Time**: 4:25 PM  
- **Elapsed Time**: 19 minutes
- **Total Vulnerabilities Detected**: 23  
  - 🔴 Critical: 0  
  - 🔶 High: 1  
  - 🟠 Medium: 2  
  - 🟡 Low: 1  
  - 🔵 Info: 19

---

## Key Findings

| Severity | Vulnerability                                      | Description & Risk | Suggested Fix |
|----------|---------------------------------------------------|--------------------|----------------|
| High     | SSL Medium Strength Cipher Suites (SWEET32)       | Supports outdated cipher suites | Disable weak ciphers |
| Medium   | SSL Certificate Signed Using Weak Hash Algorithm  | Vulnerable to forgery | Use SHA-256 or stronger |
| Medium   | SMB Signing Not Required                          | Allows man-in-the-middle attacks | Enforce SMB signing |
| Low      | SSL Certificate with RSA <2048 bits               | Weak key length | Use 2048-bit or higher keys |
| Info     | Multiple SSL/TLS & SMB configuration warnings     | Legacy settings enabled | Disable outdated protocols |

---

## Grouped Vulnerability Example: SSL (Multiple Issues)

Nessus grouped 9 SSL-related vulnerabilities, including:
- SWEET32 cipher support
- Self-signed and untrusted certificates
- Use of weak encryption algorithms
- RSA keys <2048-bit

**Fix Recommendations**:
- Disable weak cipher suites and CBC modes
- Use valid certificates from a trusted Certificate Authority
- Enforce only TLS 1.2+ and forward secrecy

---

## 📁 Screenshots

All screenshots are located in the `screenshots/` folder:

| Filename                             | Description                                  |
|--------------------------------------|----------------------------------------------|
| `01_scan_overview_and_vulnerability_list.png` | Scan summary and full vulnerability list    |
| `02_medium_ssl_weak_hash.png`        | Details of SSL weak hash vulnerability       |
| `03_medium_smb_signing.png`          | Details of SMB signing not required          |
| `04_mixed_tls_ssl_issues.png`        | Details of grouped SSL/TLS issues            |
| `05_export_options.png`              | Export window showing HTML/CSV options       |

---

## Report Export

The full scan report is saved in the `report/` folder as:

- `Nessus_Localhost_Report.html` (Complete list of detected vulnerabilities)

> ⚠️ Note: PDF export is not available in the free version of Nessus Essentials. Hence, HTML format was used.

---

## Key Learnings

- Understood how to install, configure, and run Nessus scans
- Learned how CVSS scoring works for vulnerability prioritization
- Identified risks on a real system and explored mitigation strategies
- Gained practical experience with vulnerability scanning and risk reporting

---

## References
- [Tenable Nessus Essentials](https://www.tenable.com/products/nessus/nessus-essentials)
- [CVSS Scoring Guide (NVD)](https://nvd.nist.gov/vuln-metrics/cvss)
- [CVE Details](https://cve.mitre.org/)
