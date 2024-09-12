# 🛡️ Security Assessment Report

## 🌐 Overview

This report covers the findings from a security assessment of [http://testphp.vulnweb.com/](http://testphp.vulnweb.com/). The assessment includes results from Nmap and SQLMap scans.

## 🕵️‍♂️ Scan Details

### Nmap Scan

| **Scanner** | **Target**               | **Service**   |
|-------------|--------------------------|---------------|
| Nmap         | 44.228.249.3             | HTTP          |

### SQLMap Scan

#### Initial SQL Injection

| **URL**                                             | **Database** | **Table** | **Dumped Data** |
|-----------------------------------------------------|--------------|-----------|-----------------|
| [http://testphp.vulnweb.com/listproducts.php?cat=1](http://testphp.vulnweb.com/listproducts.php?cat=1) | acuart       | users     | [users.csv](#)  |

**SQLMap Findings for 'users' Table**

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

| **URL**                        | **Found Tables**   |
|--------------------------------|--------------------|
| [http://testphp.vulnweb.com/](http://testphp.vulnweb.com/) | artists, carts, guestbook, categ, pictures |

**SQLMap Findings for Other Tables**

| **Table**    | **Entries** |
|--------------|-------------|
| artists      | 3 entries   |
| carts        | 0 entries   |
| guestbook    | 0 entries   |
| categ        | [categ.csv](#)  |
| pictures     | 7 entries   |

**Note:** CSV files for each table are stored under `/home/kali/.local/share/sqlmap/output/testphp.vulnweb.com/dump/acuart/`.

## ⚠️ Vulnerabilities

- **SQL Injection**: The application is vulnerable to SQL injection, which allows an attacker to extract sensitive information from the database.
- **Data Exposure**: The `users` table data is accessible and includes sensitive information such as email addresses and hashed passwords.

## 🚀 Recommendations

- **Sanitize User Inputs**: Ensure all user inputs are properly sanitized and validated.
- **Use Prepared Statements**: Implement prepared statements or parameterized queries to mitigate SQL injection risks.
- **Encrypt Sensitive Data**: Use strong encryption for sensitive data, including passwords.

For further details or assistance, please contact the security team.
