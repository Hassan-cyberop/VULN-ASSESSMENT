# 🛡️ SQL Injection Report

## 🌐 Target URL
- **Website:** [superyachtcoatings.com](https://superyachtcoatings.com)
- **Technology:** LiteSpeed, PHP 7.4.33

## 🗄️ Database Information
| **Database Management System (DBMS)** | **Version**       |
|---------------------------------------|-------------------|
| MySQL                                 | >= 5.0.12         |

## 📚 Extracted Databases
| **Database Name**      | **Description** |
|------------------------|-----------------|
| `information_schema`   | System metadata |
| `performance_schema`   | Performance data|
| `superyac_lfdkshxkc`   | Application data|

## 📋 Tables Extracted
| **Database**            | **Table**            | **Entries**  |
|-------------------------|----------------------|--------------|
| `information_schema`     | `ST_UNITS_OF_MEASURE`| 47 entries   |
| `information_schema`     | `PLUGINS`            | 48 entries   |

## ⚙️ SQL Injection Details
| **Parameter**       | **Injection Type**                       | **Technique**                                  |
|---------------------|------------------------------------------|------------------------------------------------|
| `id`                | Boolean-based blind                      | WHERE or HAVING clause                         |
| `id`                | Error-based                              | EXP, JSON_KEYS, FLOOR, UPDATEXML, EXTRACTVALUE |
| `id`                | Time-based blind                         | SLEEP queries                                  |
| `id`                | UNION query                              | Generic UNION query (NULL)                     |

## 📑 Summary of Vulnerabilities
- **Parameter**: `id` is vulnerable to SQL injection.
- **Techniques Used**: Boolean-based blind, Error-based, Time-based blind, UNION query.

## 🚨 Legal Disclaimer
*The use of this report for illegal activities without prior consent from the target is against the law. The author assumes no responsibility for any misuse or damages.*

---

### 👨‍💻 Author
- [Hassan Raza]

### 📅 Date of Report
- August 21, 2024
