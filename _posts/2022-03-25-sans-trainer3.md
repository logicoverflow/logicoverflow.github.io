---
layout: single
title: "Trainer: Levels 0x13 - 0x16"
header:
  overlay_image: cyber-newlocks.jpg
---

<p align="center"><img src="/images/sans-new2cyber-logo.png"></p>

## 0x13 Level
10 (Linux)

### Challenge

The password to level

Note: Not the standard flag format

author: [@nopresearcher](https://twitter.com/NopResearcher)

### Solution

```console
Welcome to Level 18

For this level you are going to continue familiarizing yourself with user artifacts.  Look in this user's home directory to see if there are any files left behind that may contain useful information.

type: man bash

level18@trainer:~$ ls -la
total 64
drwxr-x---  5 level18 level18 4096 Mar 24 18:04 .
drwxr-xr-x 26 root    root    4096 Aug 22  2021 ..
-r--r--r--  1 level19 level18  299 Aug 23  2021 .bash_history
-rw-r--r--  1 level18 level18  220 Apr 18  2019 .bash_logout
-rw-r--r--  1 level18 level18 3526 Apr 18  2019 .bashrc
drwx------  3 level18 level18 4096 Mar 24 14:15 .gnupg
-r--r-----  1 level18 level18  504 Aug 23  2021 helpme
-rw-------  1 level18 level18 1812 Mar 23 20:04 key.txt
-rw-------  1 level18 level18   38 Mar 24 14:17 .lesshst
drwxr-xr-x  3 level18 level18 4096 Sep 15  2021 .local
-rw-r--r--  1 level18 level18   15 Mar 23 21:15 plain
-rw-r--r--  1 level18 level18  807 Apr 18  2019 .profile
drwx------  2 level18 level18 4096 Mar 24 17:57 .ssh
-rwx--x--x  1 level18 level18 7735 Mar 24 18:04 .viminfo
-r--r-----  1 level18 level18  246 Aug 23  2021 welcome_message

level18@trainer:~$ cat .bash_history
whoami
uanme -a
w
id
ps -ef
netstat -an
cat /proc/version
cat /etc/*-release
pwd
ls -la
cat /etc/profile
cat ~/.bashrc
awk -F ":" '!/nologin/{print $1}' /etc/passwd
find / -perm -g=s -type f 2>/dev/null
ssh level19@localhost
b06a246b0646b337f319316b9232151c
whoami
ssh level19@127.0.0.1
pwd
ls -la
```

__Flag:__ ```b06a246b0646b337f319316b9232151c```

## 0x14 Level
10 (Linux)

### Challenge

The password to level

Note: Not the standard flag format

author: [@nopresearcher](https://twitter.com/NopResearcher)

### Solution

```console
Welcome to Level 19

For this level you are going to continue familiarizing yourself with user artifacts.  Look in this user's home directory to see if there are any files left behind that may contain useful information.

type: man ssh

level19@trainer:~$ cd .ssh

level19@trainer:~/.ssh$ ls -la
total 16
drwxr-x--- 2 level19 level19 4096 Jun 27 18:34 .
drwxr-x--- 5 level19 level19 4096 Jun 27 20:02 ..
-rw-r--r-- 1 level19 level19 1502 Jun 27 18:34 known_hosts
-rw------- 1 level19 level19 1811 Mar  3 23:54 level20_id_rsa

level19@trainer:~/.ssh$ ssh -i level20_id_rsa  level20@localhost

level20@trainer:~$ ls -la
total 52
drwxr-x---  6 level20 level20 4096 Jun 27 20:36 .
drwxr-xr-x 26 root    root    4096 Mar  5 10:06 ..
-rw-r-----  1 level20 level20 2048 Jun 27 20:25 backup.tar.gz
-rw-rw----  1 level21 level20 2048 Mar  4 22:39 backup.tgz
drwx------  3 level20 level20 4096 Jun  5 16:31 .config
drwx------  3 level20 level20 4096 May 30 17:28 .gnupg
-r--r-----  1 level20 level20  466 Mar 24 13:30 helpme
-rw-rw----  1 level20 level20   64 Mar  4 00:22 level20_password
-rw-r--r--  1 level20 level20   32 Mar  4 22:20 level21_password
drwxr-xr-x  3 level20 level20 4096 Jun 27 17:41 .local
drwxr-x---  2 level20 level19 4096 Jun 27 16:05 .ssh
-rw-------  1 level20 level20  798 Jun 27 18:58 .viminfo
-r--r-----  1 level20 level20  260 Mar  4 22:39 welcome_message
level20@trainer:~$ cat level20_password 
The password for level20 is:

5cf82d972614f73422f899f90cfce80f
```

__Flag:__ ```5cf82d972614f73422f899f90cfce80f```

## 0x15 Level
10 (Linux)

### Challenge

The password to level

Note: Not the standard flag format

author: [@nopresearcher](https://twitter.com/NopResearcher)

### Solution

```console
Welcome to Level 20

For this level you are going to continue familiarizing yourself with user artifacts.  Look in this user's home directory to see if there are any files left behind that may contain useful information.

type: man file
      man tar

level20@trainer:~$ ls -la
total 51
drwxr-x---  3 level20 level20 4096 Mar 24 23:56 .
drwxr-xr-x 26 root    root    4096 Aug 22  2021 ..
-rw-rw----  1 level21 level20 2048 Aug 23  2021 backup.tgz
-rw-r--r--  1 level20 level20  220 Apr 18  2019 .bash_logout
-rw-r--r--  1 level20 level20 3526 Apr 18  2019 .bashrc
-rw-r--r--  1 level20 level20    0 Mar 24 22:02 .cloud-locale-test.skip
-r--r-----  1 level20 level20  466 Aug 23  2021 helpme
-rw-------  1 level20 level20   32 Mar 24 18:10 .lesshst
-rw-rw----  1 level20 level20   64 Aug 23  2021 level20_password
-rw-r--r--  1 level20 level20  807 Apr 18  2019 .profile
drwxr-x---  2 level20 level19 4096 Nov  6 19:01 .ssh
-rw-------  1 level20 level20 1407 Feb  5 21:01 .viminfo
-r--r-----  1 level20 level20  260 Aug 23  2021 welcome_message

level20@trainer:~$ tar -xvf backup.tgz
level21_password

level20@trainer:~$ cat level21_password
65230da2ead4ba2ed76ee2605cadcd4d
```

__Flag:__ ```65230da2ead4ba2ed76ee2605cadcd4d```

## 0x16 Level
10 (Linux)

### Challenge

The password to level

Note: Not the standard flag format

author: [@nopresearcher](https://twitter.com/NopResearcher)

### Solution

```console
Welcome to Level 21

For this level you are going to continue familiarizing yourself with user artifacts.  Look in this user's home directory to see if there are any files left behind that may contain useful information.

type: man file

level21@trainer:~$ ls -la
total 48
drwxr-x---  4 level21 level21 4096 Mar 24 16:36 .
drwxr-xr-x 26 root    root    4096 Aug 22  2021 ..
-rw-r--r--  1 level21 level21  220 Apr 18  2019 .bash_logout
-rw-r--r--  1 level21 level21 3526 Apr 18  2019 .bashrc
drwx------  3 level21 level21 4096 Mar 24 14:19 .gnupg
-r--r-----  1 level21 level21  561 Aug 23  2021 helpme
-rw-rw----  1 level22 level21   62 Aug 23  2021 mybackup
-rwxrwx--x  1 level21 level21   33 Aug 23  2021 mybackup.out
-rw-r--r--  1 level21 level21  807 Apr 18  2019 .profile
drwx------  2 level21 level21 4096 Nov  6 19:03 .ssh
-rw-------  1 level21 level21  703 Feb  5 18:38 .viminfo
-r--r-----  1 level21 level21  247 Aug 23  2021 welcome_message

level21@trainer:~$ cat mybackup
BZh91AY&SY&�I� "��&��!�L,U���8�V><�?rE8P�&�/

level21@trainer:~$ cat mybackup.out
643b2616b33de99b179c33950970d519
```

__Flag:__ ```643b2616b33de99b179c33950970d519```
