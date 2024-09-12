# 🔍 Vulnerability Report: PHP Test Server

## 🛡️ Overview

This report presents the findings from a Vulnerability assessment of [http://testphp.vulnweb.com/](http://testphp.vulnweb.com/), targeting the server at IP address 44.228.249.3.

## 🕵️‍♂️ Scan Details

| **Scanner** | **Target**      | **Service**   |
|-------------|-----------------|---------------|
| Nmap 7.94SVN | 44.228.249.3    | HTTP (nginx 1.19.0) |

## 🔍 Vulnerabilities Identified

### 1. 🚨 Phusion Passenger Vulnerabilities

| **CVE**        | **Description**                                            |
|----------------|------------------------------------------------------------|
| CVE-2013-2070 | Race condition in Phusion Passenger up to 5.3.1.          |
| CVE-2012-2089 | Insecure access control in passenger-install-nginx-module.|

### 2. 🛡️ nginx Vulnerabilities

| **CVE**        | **Description**                                            |
|----------------|------------------------------------------------------------|
| CVE-2013-2070 | Denial of service and info disclosure via crafted proxy response. |
| CVE-2012-2089 | Buffer overflow in `ngx_http_mp4_module`.                 |
| CVE-2012-1180 | Use-after-free vulnerability allowing info disclosure.    |
| CVE-2013-2028 | Denial of service and code execution via chunked Transfer-Encoding. |
| CVE-2011-4963 | Security bypass allowing access to restricted files.      |

### 3. 📝 Additional Vulnerabilities

| **Source**        | **Details**                                     |
|-------------------|-------------------------------------------------|
| SecurityFocus     | Various denial of service and info disclosure. |
| IBM X-Force       | Buffer overflow and info disclosure issues.    |
| Exploit-DB        | Remote exploits and denial of service.         |

## 📚 References

- [VulDB](https://vuldb.com)
- [MITRE CVE](https://cve.mitre.org)
- [SecurityFocus](https://www.securityfocus.com/bid/)
- [IBM X-Force](https://exchange.xforce.ibmcloud.com)
- [Exploit-DB](https://www.exploit-db.com)
- [OpenVAS (Nessus)](http://www.openvas.org)
- [SecurityTracker](https://www.securitytracker.com)
- [OSVDB](http://www.osvdb.org)

## 🚀 Conclusion

The assessment revealed critical vulnerabilities in the nginx server. Immediate action is advised to address these issues and improve security.

---

For further details or assistance, please contact us.
