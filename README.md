# Metasploit-for-reconnaissance
# Metasploit
Metasploit for reconnaissance in pentesting

# AIM:

To get introduced to Metasploit Framework and to  perform reconnaissance  in pentesting .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## EXECUTION STEPS AND ITS OUTPUT:
Find out the ip address of the attackers system


## OUTPUT:

![1output](https://github.com/kiruthika512/Metasploit-for-reconnaissance/assets/135616605/c93a8664-2ea6-4a5d-82d1-af07344d3bfb)
Invoke msfconsole:
![2output](https://github.com/kiruthika512/Metasploit-for-reconnaissance/assets/135616605/3671a24a-5bc6-4d4d-877a-3fe6ee368d15)
Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.
![3output](https://github.com/kiruthika512/Metasploit-for-reconnaissance/assets/135616605/da28e207-b984-42cf-8d69-50d7430e9864)
Port Scanning:
Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000
OUTPUT:
![4output](https://github.com/kiruthika512/Metasploit-for-reconnaissance/assets/135616605/523cad32-cbee-46d0-951e-d1b1ac84c004)
the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24
OUTPUT:
![5output](https://github.com/kiruthika512/Metasploit-for-reconnaissance/assets/135616605/e99e3bab-1333-4ba8-9dd3-16c1a38954bc)

Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l
OUTPUT:
![6output](https://github.com/kiruthika512/Metasploit-for-reconnaissance/assets/135616605/756ffd58-6e70-4bc4-b93b-187fe3773f39)
Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit

The info command provides information regarding a module or platform,
OUTPUT:
![7output](https://github.com/kiruthika512/Metasploit-for-reconnaissance/assets/135616605/213d5043-2946-49d6-9deb-dac03db7f855)
Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init
MYSQL ENUMERATION
Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>

![8output](https://github.com/kiruthika512/Metasploit-for-reconnaissance/assets/135616605/65d1c676-aca9-4891-b776-8a38907119ce)
Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql

![9output](https://github.com/kiruthika512/Metasploit-for-reconnaissance/assets/135616605/223282ec-6939-45db-99ba-2ff4a8e028aa)
use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version
![10output](https://github.com/kiruthika512/Metasploit-for-reconnaissance/assets/135616605/bfe29db9-4c6d-40d7-97cf-0087318eaa55)
Use the set rhosts command to set the parameter and run the module, as follows:
![11output](https://github.com/kiruthika512/Metasploit-for-reconnaissance/assets/135616605/b18f70b3-a82b-43e9-949a-edf17abeaf82)

After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.
![12output](https://github.com/kiruthika512/Metasploit-for-reconnaissance/assets/135616605/a9584574-ef46-4efd-98fb-ce140dc94906)
set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true
![13output](https://github.com/kiruthika512/Metasploit-for-reconnaissance/assets/135616605/353edb02-b87e-4ad5-9a32-69d3c307f863)












## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
