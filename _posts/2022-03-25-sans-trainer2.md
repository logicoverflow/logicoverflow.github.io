---
layout: single
title: "Trainer: Levels 0x0A - 0x12"
header:
  overlay_image: cyber-newlocks.jpg
---

<p align="center"><img src="/images/sans-new2cyber-logo.png"></p>

## 0x0A Level
10 (Linux)

### Challenge

The password to level

Note: Not the standard flag format

author: [@nopresearcher](https://twitter.com/NopResearcher)

### Solution

```console
Welcome to Level 9

First a bit of history.  RockYou was a social media site that suffered a security breach in 2009, losing 32 million passwords.  They were storing all the user credentials in plain text in their database.  At the time this was the largest breach of passwords and allowed for academic research and password analysis with real data.  These passwords were eventually organized into a password list that is commonly used for cracking passwords.

For this level we want to find the line number in the rock you wordlist where the password "evilhacker" is found.  That line number is the password for level 10.  The wordlist can be found at /usr/share/wordlists/rockyou.txt (it's in the same place on kali too) Grep uses a 1-based numbering system meaning the first line is 1 and not 0.

type: man grep

level9@trainer:~$ ls
helpme  welcome_message

level9@trainer:~$ grep -in "evilhacker" /usr/share/wordlists/rockyou.txt
955830:evilhacker
```

__Flag:__ ```955830```

## 0x0B Level
10 (Linux)

### Challenge

The password to level

Note: Not the standard flag format

author: [@nopresearcher](https://twitter.com/NopResearcher)

### Solution

```console
Welcome to Level 10

For this level you are given a log file from the program fail2ban.  Fail2ban is used monitor log files for suspicious activity like too many failed logins.  It is commonly deployed for use with Apache or SSH.  After a configured number of attempts it will create an iptables (linux firewall) rule to block the ip from communicating with the device for a period of time.

The log file is located in your home directory and is called fail2ban.log.  The password to level 11 is the number of times 112.85.42.94 was banned.

type: man grep
      man wc
      
level10@trainer:~$ head -n 25 fail2ban.log
2019-11-29 18:08:28,460 fail2ban.server         [10950]: INFO    --------------------------------------------------
2019-11-29 18:08:28,460 fail2ban.server         [10950]: INFO    Starting Fail2ban v0.10.2
2019-11-29 18:08:28,466 fail2ban.database       [10950]: INFO    Connected to fail2ban persistent database '/var/lib/fail2ban/fail2ban.sqlite3'
2019-11-29 18:08:28,468 fail2ban.jail           [10950]: INFO    Creating new jail 'sshd'
2019-11-29 18:08:28,488 fail2ban.jail           [10950]: INFO    Jail 'sshd' uses pyinotify {}
2019-11-29 18:08:28,492 fail2ban.jail           [10950]: INFO    Initiated 'pyinotify' backend
2019-11-29 18:08:28,493 fail2ban.filter         [10950]: INFO      maxLines: 1
2019-11-29 18:08:28,512 fail2ban.server         [10950]: INFO    Jail sshd is not a JournalFilter instance
2019-11-29 18:08:28,512 fail2ban.filter         [10950]: INFO    Added logfile: '/var/log/auth.log' (pos = 6678, hash = e00851e7f7b891dedb8d3243544192be8c9f2b55)
2019-11-29 18:08:28,513 fail2ban.filter         [10950]: INFO      encoding: UTF-8
2019-11-29 18:08:28,513 fail2ban.filter         [10950]: INFO      maxRetry: 4
2019-11-29 18:08:28,513 fail2ban.filter         [10950]: INFO      findtime: 600
2019-11-29 18:08:28,514 fail2ban.actions        [10950]: INFO      banTime: 60
2019-11-29 18:08:28,516 fail2ban.jail           [10950]: INFO    Jail 'sshd' started
2019-11-29 18:44:52,739 fail2ban.filter         [10950]: INFO    [sshd] Found 144.202.34.43 - 2019-11-29 18:44:52
2019-11-29 18:44:52,749 fail2ban.filter         [10950]: INFO    [sshd] Found 144.202.34.43 - 2019-11-29 18:44:52
2019-11-29 18:44:55,454 fail2ban.filter         [10950]: INFO    [sshd] Found 144.202.34.43 - 2019-11-29 18:44:55
2019-11-29 18:58:49,715 fail2ban.filter         [10950]: INFO    [sshd] Found 144.202.34.43 - 2019-11-29 18:58:49
2019-11-29 18:58:49,716 fail2ban.filter         [10950]: INFO    [sshd] Found 144.202.34.43 - 2019-11-29 18:58:49
2019-11-29 18:58:51,475 fail2ban.filter         [10950]: INFO    [sshd] Found 144.202.34.43 - 2019-11-29 18:58:51
2019-11-29 19:01:43,988 fail2ban.filter         [10950]: INFO    [sshd] Found 144.202.34.43 - 2019-11-29 19:01:43
2019-11-29 19:01:44,362 fail2ban.actions        [10950]: NOTICE  [sshd] Ban 144.202.34.43
2019-11-29 19:01:46,696 fail2ban.filter         [10950]: INFO    [sshd] Found 144.202.34.43 - 2019-11-29 19:01:46
2019-11-29 19:02:44,539 fail2ban.actions        [10950]: NOTICE  [sshd] Unban 144.202.34.43
2019-11-29 19:05:13,989 fail2ban.filter         [10950]: INFO    [sshd] Found 144.202.34.43 - 2019-11-29 19:05:13

level10@trainer:~$ grep "Ban 112.85.42.94" fail2ban.log > banned.txt

level10@trainer:~$ wc -l banned.txt
192 banned.txt
```

__Flag:__ ```192```

## 0x0C Level
10 (Linux)

### Challenge

The password to level

Note: Not the standard flag format

author: [@nopresearcher](https://twitter.com/NopResearcher)

### Solution

```console
Welcome to Level 11

For this level you are given a file that contains the password to the next level.  The password is a md5 hash.  Research md5 hashes and find it in the file.

type: man grep
      man md5sum
      google md5 hash

level11@trainer:~$ ls
checkmd5.md5  helpme  index.html  md5find  welcome_message

level11@trainer:~$ awk 'length($1) == 32 { print $1 }' md5find > results.txt

level11@trainer:~$ cat results.txt
0982e2a869857644074d06b1a4fd1bea
```

__Flag:__ ```0982e2a869857644074d06b1a4fd1bea```

## 0x0D Level
10 (Linux)

### Challenge

The password to level

Note: Not the standard flag format

author: [@nopresearcher](https://twitter.com/NopResearcher)

### Solution

```console
Welcome to Level 12

For this level you are going to find SUID and SGID binaries in common locations.  This is a common privilege escalation technique seen in CTFs and real world.  Remember the user you are looking to escalate privileges to is level13.

type: man find
      google SUID
      google SGID

level12@trainer:~$ find / -perm -u=s -type f 2>/dev/null
/usr/lib/dbus-1.0/dbus-daemon-launch-helper
/usr/lib/openssh/ssh-keysign
/usr/sbin/mysecret
/usr/bin/chsh
/usr/bin/mount
/usr/bin/umount
/usr/bin/newgrp
/usr/bin/su
/usr/bin/chfn
/usr/bin/gpasswd
/usr/bin/sudo

level12@trainer:~$ find / -perm -u=s -type f 2>/dev/null
/usr/lib/dbus-1.0/dbus-daemon-launch-helper
/usr/lib/openssh/ssh-keysign
/usr/sbin/mysecret
/usr/bin/chsh
/usr/bin/mount
/usr/bin/umount
/usr/bin/newgrp
/usr/bin/su
/usr/bin/chfn
/usr/bin/gpasswd
/usr/bin/sudo

level12@trainer:~$ cd /usr/sbin/

level12@trainer:/usr/sbin$ ./mysecret
f4736e1eb28b1d9055c5f5d58a49b5a6
```

__Flag:__ ```f4736e1eb28b1d9055c5f5d58a49b5a6```

## Ox0E Level
10 (Linux)

### Challenge

The password to level

Note: Not the standard flag format

author: [@nopresearcher](https://twitter.com/NopResearcher)

### Solution

```console
Welcome to Level 13

For this level you are going to familiarize yourself with environment variables.  They are used for a wide variety of applications.  Specifically, they can be used for docker and cloud providers to store credentials.  They password to level 14 is for Amazon and is the one that ends with ID.

type: man environ
      google environment variables

level13@trainer:~$ ls
helpme  mypassword.txt  welcome_message

level13@trainer:~$ cat mypassword.txt
f4736e1eb28b1d9055c5f5d58a49b5a6
```

This flag is a red herring as we were informed that we would be working with environment variables. Furthermore, we're told the password is for Amazon and ends with ID.

```console
level13@trainer:~$ env
SHELL=/bin/bash
HISTTIMEFORMAT=%Y-%m-%d %T
AWS_DEFAULT_REGION=us-west-2
PWD=/home/level13
LOGNAME=level13
HOME=/home/level13
LANG=en_US.UTF-8
LS_COLORS=rs=0:di=01;34:ln=01;36:mh=00:pi=40;33:so=01;35:do=01;35:bd=40;33;01:cd=40;33;01:or=40;31;01:mi=00:su=37;41:sg=30;43:ca=30;41:tw=30;42:ow=34;42:st=37;44:ex=01;32:*.tar=01;31:*.tgz=01;31:*.arc=01;31:*.arj=01;31:*.taz=01;31:*.lha=01;31:*.lz4=01;31:*.lzh=01;31:*.lzma=01;31:*.tlz=01;31:*.txz=01;31:*.tzo=01;31:*.t7z=01;31:*.zip=01;31:*.z=01;31:*.dz=01;31:*.gz=01;31:*.lrz=01;31:*.lz=01;31:*.lzo=01;31:*.xz=01;31:*.zst=01;31:*.tzst=01;31:*.bz2=01;31:*.bz=01;31:*.tbz=01;31:*.tbz2=01;31:*.tz=01;31:*.deb=01;31:*.rpm=01;31:*.jar=01;31:*.war=01;31:*.ear=01;31:*.sar=01;31:*.rar=01;31:*.alz=01;31:*.ace=01;31:*.zoo=01;31:*.cpio=01;31:*.7z=01;31:*.rz=01;31:*.cab=01;31:*.wim=01;31:*.swm=01;31:*.dwm=01;31:*.esd=01;31:*.jpg=01;35:*.jpeg=01;35:*.mjpg=01;35:*.mjpeg=01;35:*.gif=01;35:*.bmp=01;35:*.pbm=01;35:*.pgm=01;35:*.ppm=01;35:*.tga=01;35:*.xbm=01;35:*.xpm=01;35:*.tif=01;35:*.tiff=01;35:*.png=01;35:*.svg=01;35:*.svgz=01;35:*.mng=01;35:*.pcx=01;35:*.mov=01;35:*.mpg=01;35:*.mpeg=01;35:*.m2v=01;35:*.mkv=01;35:*.webm=01;35:*.ogm=01;35:*.mp4=01;35:*.m4v=01;35:*.mp4v=01;35:*.vob=01;35:*.qt=01;35:*.nuv=01;35:*.wmv=01;35:*.asf=01;35:*.rm=01;35:*.rmvb=01;35:*.flc=01;35:*.avi=01;35:*.fli=01;35:*.flv=01;35:*.gl=01;35:*.dl=01;35:*.xcf=01;35:*.xwd=01;35:*.yuv=01;35:*.cgm=01;35:*.emf=01;35:*.ogv=01;35:*.ogx=01;35:*.aac=00;36:*.au=00;36:*.flac=00;36:*.m4a=00;36:*.mid=00;36:*.midi=00;36:*.mka=00;36:*.mp3=00;36:*.mpc=00;36:*.ogg=00;36:*.ra=00;36:*.wav=00;36:*.oga=00;36:*.opus=00;36:*.spx=00;36:*.xspf=00;36:
AWS_SECRET_ACCESS_KEY=2fE3dasswJalrXs2UtnFEMIs/gK7MDENG/bPxRfiCY
TERM=xterm-256color
USER=level13
SHLVL=1
AWS_ACCESS_KEY_ID=0ea027e3835aa87a4a47465321c5fe75
PATH=/usr/local/bin:/usr/bin:/bin:/usr/local/games:/usr/games
MAIL=/var/mail/level13
_=/usr/bin/env

level13@trainer:~$ env | grep ID
AWS_ACCESS_KEY_ID=0ea027e3835aa87a4a47465321c5fe75
```

__Flag:__ ```0ea027e3835aa87a4a47465321c5fe75```

## 0x0F Level
10 (Linux)

### Challenge

The password to level

Note: Not the standard flag format

author: [@nopresearcher](https://twitter.com/NopResearcher)

### Solution

```console
Welcome to Level 14

For this level you are going to familiarize yourself with the kernel version.  We are just looking for the Kernel and Major version (the first two sets of numbers) example: if the version is 2.62.26.1 the password will be 2.62

Understanding Kernel versions can help when search for exploits with tools like searchsploit or exploitdb (Sorry, there isn't any kernel exploits for this box, I hope)

type: man uname
      google linux kernel

level14@trainer:~$ uname -a
Linux trainer 4.19.0-19-cloud-amd64 #1 SMP Debian 4.19.232-1 (2022-03-07) x86_64 GNU/Linux
```

__Flag:__ ```4.19```

## 0x10 Level
10 (Linux)

### Challenge

The password to level

Note: Not the standard flag format

author: [@nopresearcher](https://twitter.com/NopResearcher)

### Solution

```console
Welcome to Level 15

For this level you are going to familiarize yourself with the distro version.  We are just looking for the distro name.  example: Fedora 31, then the password would be Fedora

Understanding distro versions can help when searching for exploits with tools like searchsploit or exploitdb (Sorry, there isn't any exploits for this distro, I hope)

type: man hostnamectl
      man lsb_release
      google linux distro

level15@trainer:~$ lsb_release -a
No LSB modules are available.
Distributor ID: Debian
Description:    Debian GNU/Linux 10 (buster)
Release:        10
Codename:       buster

level15@trainer:~$ hostnamectl
   Static hostname: trainer
         Icon name: computer-vm
           Chassis: vm
        Machine ID: 4f7efe5cdd5741dcbc6e4ea27624480c
           Boot ID: 81cbb41b1d704f6eafe2eb025e7fc629
    Virtualization: kvm
  Operating System: Debian GNU/Linux 10 (buster)
            Kernel: Linux 4.19.0-19-cloud-amd64
      Architecture: x86-64
```

__Flag:__ ```Debian```

## 0x11 Level
10 (Linux)

### Challenge

The password to level

Note: Not the standard flag format

author: [@nopresearcher](https://twitter.com/NopResearcher)

### Solution

```console
Welcome to Level 16

For this level you are going to familiarize yourself with the aliases.  They can be very useful and can be used for a variety of actions to speed up your workflow.  They can also be very dangerous.

type: google alias

level16@trainer:~$ alias
alias bc='bc -l'
alias devbox='sshpass -p 6b39034a8045ed996a436f8d09031522 ssh level17@trainer.threatsims.com'
alias grep='grep --color=auto'
alias ls='ls --color=auto'
alias mkdir='mkdir -pv'

level16@trainer:~$ cat .bashrc | grep alias
# enable color support of ls and also add handy aliases
    alias ls='ls --color=auto'
    #alias dir='dir --color=auto'
    #alias vdir='vdir --color=auto'
    #alias grep='grep --color=auto'
    #alias fgrep='fgrep --color=auto'
    #alias egrep='egrep --color=auto'
# some more ls aliases
#alias ll='ls -l'
#alias la='ls -A'
#alias l='ls -CF'
# ~/.bash_aliases, instead of adding them here directly.
if [ -f ~/.bash_aliases ]; then
    . ~/.bash_aliases
alias devbox='sshpass -p 6b39034a8045ed996a436f8d09031522 ssh level17@trainer.threatsims.com'
alias grep='grep --color=auto'
alias bc='bc -l'
alias mkdir='mkdir -pv'
```

__Flag:__ ```6b39034a8045ed996a436f8d09031522```

## 0x12 Level
10 (Linux)

### Challenge

The password to level

Note: Not the standard flag format

author: [@nopresearcher](https://twitter.com/NopResearcher)

### Solution

```console
Welcome to Level 17

For this level you are going to familiarize yourself with user artifacts.  Look in this user's home directory to see if there are any files left behind that may contain useful information.

type: man vim

level17@trainer:~$ ls -la
total 256
drwxr-x---  6 level17 level17  4096 Mar 24 18:43 .
drwxr-xr-x 26 root    root     4096 Aug 22  2021 ..
-rw-r--r--  1 level17 level17     0 Nov  6 18:16 :
-rw-r--r--  1 level17 level17   220 Apr 18  2019 .bash_logout
-rw-r--r--  1 level17 level17  3526 Apr 18  2019 .bashrc
-rw-r--r--  1 level17 level17     0 Mar 24 18:40 .cloud-locale-test.skip
drwx------  3 level17 level17  4096 Mar 23 19:50 .config
-r--r-----  1 level17 level17   533 Aug 23  2021 helpme
-rw-r--r--  1 level17 level17   807 Apr 18  2019 .profile
drwxr-xr-x  2 level17 level17  4096 Mar 23 21:20 .vim
-r--r--r--  1 level18 level17  1289 Aug 23  2021 .viminfo
-r--r-----  1 level17 level17   234 Aug 23  2021 welcome_message

level17@trainer:~$ cat .viminfo
# This viminfo file was generated by Vim 8.1.
# You may edit it if you're careful!

# Viminfo version
|1,4

# Value of 'encoding' when this file was written
*encoding=utf-8

# hlsearch on (H) or off (h):
~h
# Command Line History (newest to oldest):
:wq
|2,0,1583196421,,"wq"

# Search String History (newest to oldest):

# Expression History (newest to oldest):

# Input Line History (newest to oldest):

# Debug Line History (newest to oldest):

# Registers:
"a      LINE    0
        ssh level18@localhost
|3,0,10,1,1,0,1583196413,"ssh level18@localhost"
""b     LINE    0
        9a42b1822710d790a393800f2896a8f7
|3,1,11,1,1,0,1583196418,"9a42b1822710d790a393800f2896a8f7"

# File marks:
'0  11  0  ~/password
|4,48,11,0,1583196421,"~/password"
'1  12  0  ~/password
|4,49,12,0,1583196243,"~/password"
'2  11  0  ~/password
|4,50,11,0,1583196243,"~/password"

# Jumplist (newest first):
-'  11  0  ~/password
|4,39,11,0,1583196421,"~/password"
-'  12  0  ~/password
|4,39,12,0,1583196368,"~/password"
-'  11  0  ~/password
|4,39,11,0,1583196243,"~/password"
-'  8  0  ~/password
|4,39,8,0,1583196224,"~/password"


# History of marks within files (newest to oldest):

> ~/password
        *       1583196420      0
        "       11      0
        ^       6       1
        .       6       1
        +       6       0
        +       3       7
        +       1       3
        +       11      0
        +       10      0
        +       9       0
        +       8       0
        +       12      0
        +       6       1
        a       1       0
        b       2       0
        c       3       0
        d       4       0
```

__Flag:__ ```9a42b1822710d790a393800f2896a8f7```
