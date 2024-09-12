# 🔍 Vulnerability Report: PHP Test Server

## 🌐 Target Information
- **Target IP Address:** `44.228.249.3`
- **Domain:** ec2-44-228-249-3.us-west-2.compute.amazonaws.com
- **Technology:** nginx 1.19.0, Phusion Passenger
- **Scan Date:** August 19, 2024

## 🔥 Vulnerability Scan Overview
Performed an Nmap service and version detection scan using the Vulscan script to identify known vulnerabilities on the target server.

### 🛡️ Nmap Scan Command
```bash
nmap -sV --script=vulscan/vulscan.nse 44.228.249.3
