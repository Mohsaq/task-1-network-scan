# Task 1 - Nmap Network Port Scanning

## 🎯 Objective
To perform a TCP SYN scan using Nmap on the local network and identify open ports, understand exposed services, and assess potential security risks.

## 🧰 Tools Used
- Nmap v7.95

## 🛠️ Commands Executed

```bash
ipconfig
nmap -sS 192.168.198.1
nmap -sS 192.168.198.1 -oN scan.txt
🔍 Nmap Scan Summary
Target Host: 192.168.198.1
Open Ports & Services:

Port	State	Service	Description
135	open	Microsoft RPC	DCOM, used for Windows network services
139	open	NetBIOS-SSN	File/printer sharing, can leak network info
445	open	Microsoft-DS	SMB protocol, vulnerable to EternalBlue
903	open	VMware-auth	VMware Authentication Daemon
2869	open	Microsoft HTTPAPI	UPnP (Universal Plug and Play) service
5432	open	PostgreSQL	PostgreSQL Database (v9.6+)

⚠️ Security Analysis
135/139/445 → Common Windows ports vulnerable to SMB-related attacks.

5432 → Exposed PostgreSQL database, could allow access to sensitive data.

2869 → UPnP port; may leak internal device info if not restricted.

903 → Used by VMware services, might be exploitable if exposed to external networks.

📸 Screenshots
Nmap scan terminal output (attached as nmap_screenshot.png)


✅ Conclusion
The scan helped identify open services and understand exposure on the internal network. Services like SMB and PostgreSQL should be tightly controlled or firewalled in production systems.

📁 Files in this Repo
scan.txt – Nmap raw output

README.md – This report

nmap_screenshot.png – Screenshot of scan in terminal

