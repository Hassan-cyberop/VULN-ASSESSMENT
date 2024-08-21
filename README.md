# SQL Injection Findings

| **Category**               | **Details**                                                                                       |
|----------------------------|---------------------------------------------------------------------------------------------------|
| **Website URL**            | [superyachtcoatings.com](https://superyachtcoatings.com)                                          |
| **Web Application Technology** | LiteSpeed, PHP 7.4.33                                                                            |
| **Backend DBMS**           | MySQL >= 5.0.12                                                                                   |
| **Databases Discovered**   | - information_schema<br>- performance_schema<br>- superyac_lfdkshxkc                               |
| **Vulnerable Parameter**   | `id`                                                                                              |
| **Injection Techniques**   | - Boolean-based blind<br>- Error-based<br>- Time-based blind<br>- UNION query injection           |
| **Extracted Data**         | **ST_UNITS_OF_MEASURE** table from `information_schema` database<br>**PLUGINS** table from `information_schema` database |
