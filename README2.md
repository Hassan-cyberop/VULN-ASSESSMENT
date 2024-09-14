# 🛡️ Security and Vulnerability Assessment Report

## 🌐 Overview

This report presents the findings from a security and vulnerability assessment of [http://testphp.vulnweb.com/](http://testphp.vulnweb.com/), targeting the server at IP address `44.228.249.3`. The assessment includes results from both **Nmap** and **SQLMap** scans, along with identified vulnerabilities and remediation recommendations.

---

## 🕵️‍♂️ Scan Details

### Nmap Scan

| **Scanner**  | **Target**    | **Service**            |
|--------------|---------------|------------------------|
| Nmap 7.94SVN | 44.228.249.3  | HTTP (nginx 1.19.0)    |

### SQLMap Scan

#### Initial SQL Injection

| **URL**                                                                                               | **Database** | **Table** | **Dumped Data** |
|-------------------------------------------------------------------------------------------------------|--------------|-----------|-----------------|
| [http://testphp.vulnweb.com/listproducts.php?cat=1](http://testphp.vulnweb.com/listproducts.php?cat=1) | acuart       | users     | [users.csv](#)  |

#### SQLMap Findings for 'users' Table

| **Column** | **Value**                     |
|------------|-------------------------------|
| cc         | 1234                          |
| cart       | e52342b347c23077892ee8c32300a77f |
| pass       | test                          |
| email      | ycce123@gmail.com             |
| phone      | 9876543210                    |
| uname      | test                          |
| name       | John Smith                    |
| address    | xyz                           |

#### SQLMap Crawl

| **URL**                        | **Found Tables**                |
|--------------------------------|---------------------------------|
| [http://testphp.vulnweb.com/](http://testphp.vulnweb.com/) | artists, carts, guestbook, categ, pictures |

#### SQLMap Findings for Other Tables

| **Table**    | **Entries**               |
|--------------|---------------------------|
| artists      | 3 entries                 |
| carts        | 0 entries                 |
| guestbook    | 0 entries                 |
| categ        | [categ.csv](#)            |
| pictures     | 7 entries                 |



---

## 🔍 Vulnerabilities Identified

### 1. 🚨 Phusion Passenger Vulnerabilities

| **CVE**        | **Description**                                            |
|----------------|------------------------------------------------------------|
| CVE-2013-2070  | Race condition in Phusion Passenger up to 5.3.1.            |
| CVE-2012-2089  | Insecure access control in passenger-install-nginx-module.  |

### 2. 🛡️ nginx Vulnerabilities

| **CVE**        | **Description**                                                |
|----------------|----------------------------------------------------------------|
| CVE-2013-2070  | Denial of service and info disclosure via crafted proxy response. |
| CVE-2012-2089  | Buffer overflow in `ngx_http_mp4_module`.                      |
| CVE-2012-1180  | Use-after-free vulnerability allowing info disclosure.        |
| CVE-2013-2028  | Denial of service and code execution via chunked Transfer-Encoding. |
| CVE-2011-4963  | Security bypass allowing access to restricted files.           |

### 3. 📝 Additional Vulnerabilities

| **Source**        | **Details**                                         |
|-------------------|-----------------------------------------------------|
| SecurityFocus     | Various denial of service and info disclosure.       |
| IBM X-Force       | Buffer overflow and info disclosure issues.          |
| Exploit-DB        | Remote exploits and denial of service.               |

---

## ⚠️ Vulnerabilities

| **Vulnerability**     | **Description**                                                                                   |
|-----------------------|---------------------------------------------------------------------------------------------------|
| SQL Injection         | The application is vulnerable to SQL injection, allowing extraction of sensitive database information. |
| Data Exposure         | The `users` table includes sensitive information such as email addresses and hashed passwords.     |

---

## 🚀 Recommendations

| **Action**             | **Description**                                                                                   |
|------------------------|---------------------------------------------------------------------------------------------------|
| Sanitize User Inputs    | Ensure all user inputs are properly sanitized and validated.                                       |
| Use Prepared Statements | Implement prepared statements or parameterized queries to mitigate SQL injection risks.            |
| Encrypt Sensitive Data  | Use strong encryption for sensitive data, including passwords.                                    |

---

## 📚 References

- [VulDB](https://vuldb.com)
- [MITRE CVE](https://cve.mitre.org)
- [SecurityFocus](https://www.securityfocus.com/bid/)
- [IBM X-Force](https://exchange.xforce.ibmcloud.com)
- [Exploit-DB](https://www.exploit-db.com)
- [OpenVAS (Nessus)](http://www.openvas.org)
- [SecurityTracker](https://www.securitytracker.com)
- [OSVDB](http://www.osvdb.org)
## 🚨 Legal Disclaimer
*The use of this report for illegal activities without prior consent from the target is against the law. The author assumes no responsibility for any misuse or damages.*

---

### 👨‍💻 Author
- Hassan Raza

### 📅 Date of Report
- August 10, 2024
