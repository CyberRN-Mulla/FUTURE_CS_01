# FUTURE_CS_01 - Task 1: Web Application Security Testing

This repository is a documentation of my work on Task 1 of my cybersecurity internship, where I performed vulnerability testing on DVWA (Damn Vulnerable Web App). Manual techniques, and scanning tools were used to identify and exploit common web application vulnerabilities, mapped them to the OWASP Top 10, and also compiled a full security assessment report.

---

## OBJECTIVE

To explore and exploit common web application flaws in a controlled environment, using industry-standard tools, and to document findinds with screenshots, impact analysis, and remediation strategies.

---

## TOOLS USED

- DVWA – Damn Vulnerable Web Application
- OWASP ZAP – Open-source vulnerability scanner
- Kali Linux (optional) – Security testing OS
- Firefox Developer Tools - Manual inspection and request capture
- Google Docs / Word - Report compilation
- Python HTTP Server - Used to host CSRF attack page

---

## VULNERABILITY TESTED

### 1. SQL Injection
- **Payload**: `' OR '1'=1 --`
- **Impact**: Authentication bypass
- **OWASP Mapping**: A01:2021 – Broken Access Control / A03:2021 – Injection
- **Remediation**: Use parameterized queries and validate input
- **Screenshot**:
  ! [SQL Injection Exploit] (sql-injection.png)

### 2. Reflected XSS
- **Payload**: `<script>alert('XSS')</script>`
- **Impact**: Medium (Could allow session hijacking, phishing, and browser exploitation).
- **OWASP Mapping**: A03:2021 – Cross-Site Scripting
- **Remediation**: Encode output and apply CSP
- **Screenshot**:
  ! [Reflected XSS] (screenshots/Ref_XSS.png)

### 3. CSRF (Successful Exploit)
- **Method**: Request replay using captured token
- **Payload**:

password_current=password

password_new=hacked123

password_conf=hacked123

Change=Change

user_token=d41d8cd98f00b204e9800998ecf8427e
- **Impact**: High (Admin password changed without consent)
- **OWASP Mapping**: A05:2021 – Security Misconfiguration
- **Remediation**: Implement anti-CSRF tokens in forms, Validate HTTP headers (e.g., Origin, Referer), Enforce SameSite cookie attributes.
- **Screenshot**:
  ![CSRF Exploit] (CRSF.png)

---

## RISK RATINGS

- SQL Injection: Critical
- Reflected XSS: Medium
- CSRF Replay: High

---

## DELIVERABLES

- Security Report with risk rating (PDF)
- OWASP Top 10 Compliance checklist
- Screenshots of each exploit
- Source code of CSRF attack page
- GitHub documentation

---

## SKILLS GAINED

- Web application vulnerability scanning
- Security documentation and reporting
- Knowledge of OWASP Top 10 threats
- Ethical hacking and penetration testing
- Threat modeling and risk analysis

---

## AUTHOR

GODSON ENRUCHI CHUKWU

Cybersecurity Intern

Location: Remote
