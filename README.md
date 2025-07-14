# Hackers-lab
🔍 Passive Reconnaissance in Ethical Hacking

## ✅ What is Passive Recon?

Passive reconnaissance is the process of collecting publicly available information about a target without directly touching or scanning the system. It is stealthy and often used in the early phases of ethical hacking.

---

## 🛠️ Tools Used

### 1. **Wappalyzer**
- **Function**: Identifies technologies used on a website (CMS, server, frameworks, JS libraries)
- **Usage**: Browser extension (Chrome/Firefox)
- **Results**:
  - Detected Apache server
  - Running PHP
  - Bootstrap + jQuery present
- **Category**: Passive

### 2. **crt.sh**
- **Function**: Displays SSL certificate history and subdomains
- **Usage**: Online search tool [https://crt.sh](https://crt.sh)
- **Results**:
  - Discovered subdomains like `admin.example.com`, `test.example.com`
  - Certificate metadata and issuers
- **Category**: Passive

---

## 🔁 Wappalyzer vs crt.sh

| Feature      | Wappalyzer                    | crt.sh                           |
|--------------|-------------------------------|----------------------------------|
| **Purpose**  | Tech stack discovery          | SSL & subdomain discovery        |
| **Method**   | Browser-based scan            | Certificate transparency logs    |
| **Usage**    | Frontend fingerprinting       | Backend intel on domains         |

---

## ⚠️ Subdomain Exploitation Techniques

### 1. Subdomain Takeover
- Occurs when a subdomain still has DNS records pointing to a third-party service (like GitHub Pages) that’s no longer active.
- Hacker can register that service and control the subdomain.

### 2. Insecure Dev or Staging Sites
- Subdomains like `dev.example.com` or `staging.example.com` may expose credentials or admin panels.

### 3. Misconfigured CORS or Headers
- Poor CORS policies can leak sensitive data from subdomains.

### 4. Information Leakage
- Exposed `.git`, `.env`, or log files under subdomains can reveal secrets.

---

## 🧪 Hands-On Summary

### 🔍 Wappalyzer
- Inspected: http://testphp.vulnweb.com
- Found tech stack: Apache, PHP, Bootstrap, jQuery

### 🔎 crt.sh
- Initial error due to query overload
- Later succeeded with more refined domain search
- Discovered valid subdomains tied to certificates

---

## 📌 Takeaways

- Passive recon is crucial to ethical hacking — it reveals a lot without alerting the target.
- Combining tools like Wappalyzer and crt.sh gives both front-end and back-end insights.
- Always document subdomain findings for follow-up active scans or potential exploits.