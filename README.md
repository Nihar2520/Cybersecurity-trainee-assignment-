# Cybersecurity-trainee-assignment-


# Security Posture Evaluation – itsecgames.com

## 📌 Problem Statement
Evaluate the security posture of the publicly hosted endpoint:

```

[http://www.itsecgames.com/](http://www.itsecgames.com/)

```

### Objectives
1. Identify vulnerabilities using publicly available tools.  
2. Detect potential misconfigurations, outdated software, and CVEs.  
3. Assess SSL/TLS configuration and certificate health.  
4. Highlight exposed information (headers, banners, error messages).  
5. Provide a prioritized list of findings with mitigation recommendations.  

---

## 🛠 Tools & Methodology
The following tools and techniques were used (passive and light active scans only, **no exploitation attempted**):

- `dig` / `whois` – DNS enumeration  
- `curl` – HTTP header and content analysis  
- `whatweb` – Technology fingerprinting  
- `openssl` / SSL Labs – TLS/SSL configuration & certificate health  
- `nikto` – Web server vulnerability scan  
- `nmap` – Service and version discovery  
- `crt.sh` – Certificate Transparency / subdomain enumeration  

Scans were performed between **26–27 Sept 2025**.

---

## 🔎 Key Findings
- **High:** Public exposure of **bWAPP** (intentionally vulnerable application).  
- **High:** Outdated **OpenSSH 6.7p1** with known CVEs (CVE-2016-0777, CVE-2016-0778).  
- **Medium:** Weak TLS configuration, expired/untrusted certificate, TLS 1.0/1.1 enabled.  
- **Medium:** Missing security headers (X-Frame-Options, HSTS), ETag inode leakage.  
- **Medium:** SPF record includes internal hostname (`mme-srv-dc1.mme.local`).  
- **Low:** DNSSEC not enabled; default Apache files exposed.  

---

## 🛡 Recommendations
- Restrict or take **bWAPP** offline (training app should not be public).  
- Upgrade/patch OpenSSH and Drupal to supported versions.  
- Replace SSL/TLS certificate; disable TLS 1.0/1.1; enable TLS 1.3.  
- Add missing security headers (HSTS, X-Frame-Options, X-Content-Type-Options).  
- Correct SPF record to remove internal references.  
- Enable DNSSEC for improved DNS integrity.  

---

## 📑 Report
The full detailed report, including evidence and screenshots, is available in:

- [`Cyber_Security_Trainee_Assignment_Final.docx`](./Cyber_Security_Trainee_Assignment_Final.docx)

---

## 🎥 Video Demonstration
A video walkthrough of the problem statement response is available here:

👉 [Google Drive Link](#)  
*(Enable access for everyone with the link.)*

---

## ⚠ Disclaimer
This project was conducted strictly for **educational purposes**.  
No exploitation was attempted. All scans were limited to passive reconnaissance and basic vulnerability detection against **itsecgames.com**, a public training environment hosting bWAPP.
