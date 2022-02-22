# DRIFTINGBLUES-CTF

## Writeup for Driftingblues ctf on vulnhub

Downloadlink : 
https://www.vulnhub.com/entry/driftingblues-7,680/

*Fast and simple root access using metasploit*

1) Locate vulnerable machine IP address by using *netdiscover*  **Ip : 192.168.18.3** (^ip address will be diffrent on your machine) 
2) Scan for open ports using *NMAP.* **nmap -sV -p- -v 192.168.18.3**

**-nmap results-**
Starting Nmap 7.91 ( https://nmap.org ) at 2021-12-01 22:16 EST

Nmap scan report for 192.168.18.3

Host is up (0.00010s latency).

Not shown: 65527 closed ports

PORT     STATE SERVICE         VERSION

22/tcp   open  ssh             OpenSSH 7.4 (protocol 2.0)

66/tcp   open  http            SimpleHTTPServer 0.6 (Python 2.7.5)

80/tcp   open  http            Apache httpd 2.4.6 ((CentOS) OpenSSL/1.0.2k-fips mod_fcgid/2.3.9 PHP/5.4.16 mod_perl/2.0.11 Perl/v5.16.3)

111/tcp  open  rpcbind         2-4 (RPC #100000)

443/tcp  open  ssl/http        Apache httpd 2.4.6 ((CentOS) OpenSSL/1.0.2k-fips mod_fcgid/2.3.9 PHP/5.4.16 mod_perl/2.0.11 Perl/v5.16.3)

2403/tcp open  taskmaster2000?

3306/tcp open  mysql           MariaDB (unauthorized)

8086/tcp open  http            InfluxDB http admin 1.7.9

MAC Address: 08:00:27:72:F5:D5 (Oracle VirtualBox virtual NIC)

-----------------------------------------------------------------------

Check port 80 and came across a website that uses the EyesOfNetwork 

Searchspolit EyesOfNetwork , found a exploit for it

Use exploit/linux/http/eyesofnetwork_autodiscovery_rce and a shell is generated 

cd root and cat flat.txt


░░░░░▄▄▄▄▀▀▀▀▀▀▀▀▄▄▄▄▄▄▄

░░░░░█░░░░░░░░░░░░░░░░░░▀▀▄

░░░░█░░░░░░░░░░░░░░░░░░░░░░█

░░░█░░░░░░▄██▀▄▄░░░░░▄▄▄░░░░█

░▄▀░▄▄▄░░█▀▀▀▀▄▄█░░░██▄▄█░░░░█

█░░█░▄░▀▄▄▄▀░░░░░░░░█░░░░░░░░░█

█░░█░█▀▄▄░░░░░█▀░░░░▀▄░░▄▀▀▀▄░█

░█░▀▄░█▄░█▀▄▄░▀░▀▀░▄▄▀░░░░█░░█

░░█░░░▀▄▀█▄▄░█▀▀▀▄▄▄▄▀▀█▀██░█

░░░█░░░░██░░▀█▄▄▄█▄▄█▄▄██▄░░█

░░░░█░░░░▀▀▄░█░░░█░█▀█▀█▀██░█

░░░░░▀▄░░░░░▀▀▄▄▄█▄█▄█▄█▄▀░░█

░░░░░░░▀▄▄░░░░░░░░░░░░░░░░░░░█

░░▐▌░█░░░░▀▀▄▄░░░░░░░░░░░░░░░█

░░░█▐▌░░░░░░█░▀▄▄▄▄▄░░░░░░░░█

░░███░░░░░▄▄█░▄▄░██▄▄▄▄▄▄▄▄▀

░▐████░░▄▀█▀█▄▄▄▄▄█▀▄▀▄

░░█░░▌░█░░░▀▄░█▀█░▄▀░░░█

░░█░░▌░█░░█░░█░░░█░░█░░█

░░█░░▀▀░░██░░█░░░█░░█░░█

░░░▀▀▄▄▀▀░█░░░▀▄▀▀▀▀█░░█


congratulations!





