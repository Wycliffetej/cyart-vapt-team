Capstone Project 
Overview

This project demonstrates a complete Vulnerability Assessment and Penetration Testing (VAPT) cycle conducted in a controlled lab environment. The objective was to identify vulnerabilities in the target system, exploit them safely, and document the findings along with remediation recommendations.

The testing environment consisted of an attacker machine running Kali Linux and a vulnerable target machine Metasploitable2.

The assessment followed the methodology of the Penetration Testing Execution Standard.

Target IP: 192.168.175.128

Tools Used

Nmap

OpenVAS

Nikto

Metasploit Framework

VAPT Phases
1 Reconnaissance

The reconnaissance phase was performed using Nmap to discover open ports and services running on the target machine.

Command used:

nmap -sV 192.168.175.128

Open ports discovered included FTP, SSH, HTTP, SMB, MySQL, and Tomcat services.

2 Vulnerability Scanning

Automated vulnerability scanning was conducted using OpenVAS and Nikto to identify potential security weaknesses in the target system.

Several vulnerabilities were discovered including outdated services and exposed web configurations.

3 Exploitation

The exploitation phase was conducted using Metasploit.

Exploit module used:

exploit/unix/ftp/vsftpd_234_backdoor

The exploit successfully established a command shell session on the target system.

4 Post Exploitation

After gaining access, system enumeration was performed to gather system information and user details.

Commands executed:

uname -a
cat /etc/passwd

These commands revealed system information and multiple user accounts on the compromised system.

Key Findings
Vulnerability	Severity
VSFTPD 2.3.4 Backdoor	Critical
Outdated Apache Version	High
Outdated PHP Version	High
HTTP TRACE Enabled	Medium
Impact

Successful exploitation allowed remote shell access to the target system. An attacker could potentially gain full control over the machine, access sensitive data, or pivot to other systems in the network.

Remediation

Update outdated services

Disable unnecessary ports

Apply regular security patches

Implement firewall restrictions

Perform regular vulnerability scanning