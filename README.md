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


## OUTPUT:
![318633603-584a6e38-f7f5-48d1-a794-e46919e7f8d8](https://github.com/Gokul0117/Metasploit-for-reconnaissance/assets/121165938/83388a44-70c7-4e61-bbdd-d47509b07a85)
Invoke msfconsole:
![318633708-8ece81bd-8d91-498d-91cc-18096809bf40](https://github.com/Gokul0117/Metasploit-for-reconnaissance/assets/121165938/2b160899-00ef-435b-b292-854323962c37)
Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.
![318633750-6d8173b7-464c-4be9-9c3c-075633e02d2b](https://github.com/Gokul0117/Metasploit-for-reconnaissance/assets/121165938/28a85605-122f-44fc-afcc-ef9b8c26d2c2)

Port Scanning: Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000 OUTPUT:

![318633849-ff252e3e-fe1e-4a93-b754-5d4ced4f68b7](https://github.com/Gokul0117/Metasploit-for-reconnaissance/assets/121165938/a0d6078d-29cf-4278-904a-367bd480f4d8)
step4: use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.
scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24 OUTPUT:

![318633950-3ee66371-ccc9-4245-b5ff-5356809e362c](https://github.com/Gokul0117/Metasploit-for-reconnaissance/assets/121165938/08399c5c-1ded-4f83-bbfc-d4449d8c3514)

Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l


## OUTPUT:
![318634001-fbb24c97-3807-46e7-b06b-c3b625967215](https://github.com/Gokul0117/Metasploit-for-reconnaissance/assets/121165938/96f67657-2e96-487b-9195-6c16e26cd09e)

Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit

The info command provides information regarding a module or platform,

OUTPUT
![318634049-97a56fd6-c08c-43d3-8816-6a1fcef38c56](https://github.com/Gokul0117/Metasploit-for-reconnaissance/assets/121165938/440e13d8-e288-4cf5-b96f-b682454ad209)

Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init

MYSQL ENUMERATION Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>

![318634104-93452bc1-249d-4a05-bda6-140c2db75eea](https://github.com/Gokul0117/Metasploit-for-reconnaissance/assets/121165938/fcb24ff7-399a-43e8-8df2-8f3bd2b7b2c5)

Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql

![318634159-fde3f8b6-db49-4248-8f77-39d61ea12557](https://github.com/Gokul0117/Metasploit-for-reconnaissance/assets/121165938/97a457a8-b469-40df-9321-0836bade9b86)
Use the set rhosts command to set the parameter and run the module, as follows:
![318634296-41895fb8-8adf-4e5d-a486-0bb7cfda2f8c](https://github.com/Gokul0117/Metasploit-for-reconnaissance/assets/121165938/7657f644-a3ff-46c4-ba96-b73589ae6cf6)
After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.

![318634349-e3a3574e-8c7e-4148-9cf5-5064b270f690](https://github.com/Gokul0117/Metasploit-for-reconnaissance/assets/121165938/e6714690-71fd-439d-872a-c55395881fe2)

set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true

![318634402-671d8b95-a4c4-4be3-a006-52c6dccf5803](https://github.com/Gokul0117/Metasploit-for-reconnaissance/assets/121165938/f8b7d83a-aca2-44df-b654-88f06c7ef341)




## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
