
**Challenge** 1:
An attacker conducted footprinting on a web application and saved the resulting report Dumpster.xlsx in the documents folder of EH Workstation-1. Your task is to analyze this report and identify the hostname associated with the IP address 173.245.59.176. (Format: aaaaa.aa.aaaaaaaaaa.aaa)
- open the Dumpster.xlsx file and filter given ip

Answer: henry.ns.cloudflare.com

**Challenge 2:**
Identify the number of live machines excluding the gateway in 192.168.10.0/24 subnet. (Format: N)
- nmap -sn 192.168.10.0/24 (Exclude first ip address)

Answer: 5

**Challenge 3:**
Identify the IP address of a Linux-based machine with port 22 open in the target network 192.168.10.0/24 (Format: NNN.NNN.NN.NNN).
- nmap -p 22 192.168.10.0/24 --open

Answer: 192.168.10.111

**Challenge 4:**
Find the IP address of the Domain Controller machine in 192.168.0.0/24. (Format: NNN.NNN.N.NNN)
- nmap -p 53 192.168.0.0/24 --open

Answer: 192.168.0.222

**Challenge 5:**
Perform a host discovery scanning and identify the NetBIOS_Domain_Name of the host at 192.168.0.222. (Format: AAAAA.AAA)
- nmap -sV -A 192.168.0.222

Answer: SKILL.CEH

**Challenge 6:**
Perform an intense scan on 192.168.0.222 and find out the DNS_Tree_Name of the machine in the network. (Format: AAAAA.AAA.aaa)
- nmap -sV -A 192.168.0.222

Answer: SKILL.CEH.com

**Challenge 7:**
While performing a security assessment against the CEHORG network, you came to know that one machine in the network is running OpenSSH and is vulnerable. Identify the version of the OpenSSH running on the machine. Note: Target network 192.168.10.0/24. (Format: N.NaN)
- nmap  -p  22  -sV 192.168.10.0/24 --open

Answer: 8.9p1

**Challenge 8:**
During a security assessment, it was found that a server was hosting a website that was susceptible to blind SQL injection attacks. Further investigation revealed that the underlying database management system of the site was MySQL. Determine the machine OS that hosted the database. Note: Target network 172.30.10.0/24 (Format: Aaaaaa)
- nmap -p 3306 172.30.10.0/24 --open  ( you find the ip of host)
- nmap -A 172.30.10.99

Answer: Ubuntu 

**Challenge 9:**
Perform an intense scan on target subnet 192.168.10.0/24 and determine the IP address of the machine hosting the MSSQL database service. (Format: NNN.NNN.NN.NNN)
- nmap -p 1433 192.168.10.0/24

Answer: 192.168.10.144

**Challenge 10:**
Perform a DNS enumeration on www.certifiedhacker.com and find out the name servers used by the domain. (Format: aaN.aaaaaaaa.aaa, aaN.aaaaaaaa.aaa)
- dig NS certifiedhacker.com   (or) use whois

Answer: ns1.bluehost.com, ns2.bluehost.com

**Challenge 11:**
Find the IP address of the machine running SMTP service on the 172.30.10.0/24 network. (Format: NNN.NN.NN.NNN)
- nmap -p 25 172.30.10.0/24 --open

Answer: 172.30.10.200

**Challenge 12:**
Perform an SMB Enumeration on 172.30.10.200 and check whether the Message signing feature is required. Give your response as Yes/No.
- nmap -p 445 -sV -A 172.30.10.200

Answer: No

**Challenge 13:**
Perform a vulnerability assessment on the 2023 CWE Top 25 most dangerous software vulnerabilities and determine the weakness ID of the last entry on the list. (Format: NNN)
- Search for ( 2023 CWE Top 25 most dangerous software vulnerabilities ) in google.
- Goto [ https://cwe.mitre.org/top25/archive/2023/2023_top25_list.html ]
- Enter last 25th id in list

Answer: 276

**Challenge 14:**
Perform vulnerability scanning for the Linux host in the 192.168.10.0/24 network using OpenVAS and find the QoD percentage of vulnerabilitiy with severity level as medium. (Format: NN)
- docker run -d -p 443:443 --name openvas mikesplain/openvas
- Add task for given network.
- Goto results after the scan

Answer: 70

**Challenge 15:**
Perform a vulnerability scan on the host at 192.168.10.144 using OpenVAS and identify any FTP-related vulnerability. (Format: AAA Aaaaaaaaa Aaaaaaaaa Aaaaa )
- docker run -d -p 443:443 --name openvas mikesplain/openvas
- Add task for given network.
- Goto results after the scan
- Filter ftp

Answer: FTP Unencrypted Cleartext Login

