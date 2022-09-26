---
layout: single
title: "OverTheWire - Bandit: Solutions 1-10"
header:
  caption: "[__OverTheWire__](http://overthewire.org/wargames/bandit)"
---

A colleague of mine informed me of this site and its various wargames it contains. Bandit reminds me of Linux Trainer, created by @NopResearcher, as the goal is to introduce or force you to learn the various general linux commands one may need in order to use and potentially hack with it.

This post will contain the solutions for the first 10 levels of Bandit. If you're learning Linux through Bandit, I urge you to really try to solve each level on your own. Only and only if you have "Tried Harder" and you're still stuck, then check out the solution and learn.

Let's get started!
## Level 0

The goal of this level is for you to log into the game using SSH. The host to which you need to connect is __bandit.labs.overthewire.org__, on port __2220__. The username is __bandit0__ and the password is __bandit0__. Once logged in, go to the Level 1 page to find out how to beat Level 1.

```console
┌──(logicoverflow㉿RZR-LP)-[~]
└─$ ssh bandit0@bandit.labs.overthewire.org -p 2220
bandit0@bandit:~$ whoami
bandit0
```

We've now obtained shell access to the server.

__Flag:__ ```ssh bandit0@bandit.labs.overthewire.org -p 2220```

## Level 0 -> 1

The password for the next level is stored in a file called __readme__ located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.

```console
bandit0@bandit:~$ ls
readme
bandit0@bandit:~$ cat readme
NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
```

We've obtained the password for bandit1. It would seem that the server does not allow us to `su` to the next user, so we'll have to `exit` and SSH directly to it.

In order to prevent me having to constantly type out the entire string, I wrote the following script, where all I have to do is enter the level number.

```shell
#!/bin/sh

if [ -z "$1" ]; then
        echo "Please enter the bandit level you wish to SSH to"
else
        ssh "bandit"$1@bandit.labs.overthewire.org -p 2220
fi
```

Now let's connect to bandit1 with the  password we just obtained.

```console
┌──(logicoverflow㉿RZR-LP)-[~]
└─$ ./bandit.sh 1
bandit1@bandit:~$ whoami
bandit1
```

__Flag:__ ```NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL```

## Level 1 -> 2

The password for the next level is stored in a file called __-__ located in the __home__ directory

```console
bandit1@bandit:~$ ls -la
total 24
-rw-r-----  1 bandit2 bandit1   33 Sep  1 06:30 -
drwxr-xr-x  2 root    root    4096 Sep  1 06:30 .
drwxr-xr-x 49 root    root    4096 Sep  1 06:30 ..
-rw-r--r--  1 root    root     220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root    root    3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root    root     807 Jan  6  2022 .profile
bandit1@bandit:~$ cat < -
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
```

__Flag:__ ```rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi```

## Level 2 -> 3

The password for the next level is stored in a file called __spaces in this filename__ located in the home directory

```console
bandit2@bandit:~$ ls -la
total 24
drwxr-xr-x  2 root    root    4096 Sep  1 06:30 .
drwxr-xr-x 49 root    root    4096 Sep  1 06:30 ..
-rw-r--r--  1 root    root     220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root    root    3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root    root     807 Jan  6  2022 .profile
-rw-r-----  1 bandit3 bandit2   33 Sep  1 06:30 spaces in this filename
bandit2@bandit:~$ cat spaces\ in\ this\ filename
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
```

__Flag:__ ```aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG```

## Level 3 -> 4

The password for the next level is stored in a hidden file in the __inhere__ directory.

```console
bandit3@bandit:~$ ls -la
total 24
drwxr-xr-x  3 root root 4096 Sep  1 06:30 .
drwxr-xr-x 49 root root 4096 Sep  1 06:30 ..
-rw-r--r--  1 root root  220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root root 3771 Jan  6  2022 .bashrc
drwxr-xr-x  2 root root 4096 Sep  1 06:30 inhere
-rw-r--r--  1 root root  807 Jan  6  2022 .profile
bandit3@bandit:~$ cd inhere/
bandit3@bandit:~/inhere$ ls -la
total 12
drwxr-xr-x 2 root    root    4096 Sep  1 06:30 .
drwxr-xr-x 3 root    root    4096 Sep  1 06:30 ..
-rw-r----- 1 bandit4 bandit3   33 Sep  1 06:30 .hidden
bandit3@bandit:~/inhere$ cat .hidden
2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe
```

__Flag:__ ```2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe```

## Level 4 - > 5

The password for the next level is stored in the only human-readable file in the __inhere__ directory. Tip: if your terminal is messed up, try the “reset” command.

```console
bandit4@bandit:~/inhere$ grep -ri [A-Z][a-z][0-9] .
grep: ./-file03: binary file matches
grep: ./-file09: binary file matches
./-file07:lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
bandit4@bandit:~/inhere$ cat < -file07
lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
```

__Flag:__ ```lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR```

## Level 5 -> 6

The password for the next level is stored in a file somewhere under the __inhere__ directory and has all of the following properties:
<ul>
<li>human-readable</li>
<li>1033 bytes in size</li>
<li>not executable</li>
</ul>

```console
bandit5@bandit:~$ cd inhere/
bandit5@bandit:~/inhere$ ls -la
total 88
drwxr-x--- 22 root bandit5 4096 Sep  1 06:30 .
drwxr-xr-x  3 root root    4096 Sep  1 06:30 ..
drwxr-x---  2 root bandit5 4096 Sep  1 06:30 maybehere00
drwxr-x---  2 root bandit5 4096 Sep  1 06:30 maybehere01
drwxr-x---  2 root bandit5 4096 Sep  1 06:30 maybehere02
drwxr-x---  2 root bandit5 4096 Sep  1 06:30 maybehere03
drwxr-x---  2 root bandit5 4096 Sep  1 06:30 maybehere04
drwxr-x---  2 root bandit5 4096 Sep  1 06:30 maybehere05
drwxr-x---  2 root bandit5 4096 Sep  1 06:30 maybehere06
drwxr-x---  2 root bandit5 4096 Sep  1 06:30 maybehere07
drwxr-x---  2 root bandit5 4096 Sep  1 06:30 maybehere08
drwxr-x---  2 root bandit5 4096 Sep  1 06:30 maybehere09
drwxr-x---  2 root bandit5 4096 Sep  1 06:30 maybehere10
drwxr-x---  2 root bandit5 4096 Sep  1 06:30 maybehere11
drwxr-x---  2 root bandit5 4096 Sep  1 06:30 maybehere12
drwxr-x---  2 root bandit5 4096 Sep  1 06:30 maybehere13
drwxr-x---  2 root bandit5 4096 Sep  1 06:30 maybehere14
drwxr-x---  2 root bandit5 4096 Sep  1 06:30 maybehere15
drwxr-x---  2 root bandit5 4096 Sep  1 06:30 maybehere16
drwxr-x---  2 root bandit5 4096 Sep  1 06:30 maybehere17
drwxr-x---  2 root bandit5 4096 Sep  1 06:30 maybehere18
drwxr-x---  2 root bandit5 4096 Sep  1 06:30 maybehere19
bandit5@bandit:~/inhere$ find . -size 1033c ! -executable -exec file {} +
./maybehere07/.file2: ASCII text, with very long lines (1000)
bandit5@bandit:~/inhere$ cat maybehere07/.file2
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
```

__Flag:__ ```P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU```

## Level 6 -> 7

The password for the next level is stored __somewhere on the server__ and has all of the following properties:
<ul>
<li>owned by user bandit7</li>
<li>owned by group bandit6</li>
<li>33 bytes in size</li>
</ul>

```console
bandit6@bandit:~$ bandit6@bandit:/$ find / -size 33c -group bandit6 -user bandit7 2>/dev/null
bandit6@bandit:~$ find / -size 33c -group bandit6 -user bandit7 2>/dev/null
/var/lib/dpkg/info/bandit7.password
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
```

__Flag:__ ```z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S```

## Level 7 -> 8

The password for the next level is stored in the file __data.txt__ next to the word __millionth__

```console
bandit7@bandit:~$ head data.txt
Weddell's       o8S2mUyOlnSJvej8IIC3Jd8qBM7jLYeL
sucks   SVP9VgB4uSJKMejmdRC2u20NI4tLC9JH
genders 11EjE7xEF0vjvMOXDFpUucGXgU706iKX
vagrants        h7Wb2ZHWx9TtGLsJIQn5IyH2A3CkcZFc
shrewed oEl7VCrKajDdbXvJrW9IVUlk2KA0GPZs
imbecile's      P7nHwuVBUWnFTXPvSpjWFlimJASMOUNa
reexamining     VQbmDcurUPB9koHHeCRugBvBpMpM6V0c
emailed 85cYMCVUneJDwT5prLClMlKT1rhqKZgj
barometers      3wKwiJ7YhZdpjypRO9kfQNmJjp66to8d
Ephesian        6KvOfHGIHnvWIwQruJXPQFhA1Plheicd
bandit7@bandit:~$ cat data.txt | grep millionth
millionth       TESKZC0XvTetK0S9xNwm25STk5iWrBvP
```

__Flag:__ ```TESKZC0XvTetK0S9xNwm25STk5iWrBvP```

## Level 8 -> 9

The password for the next level is stored in the file __data.txt__ and is the only line of text that occurs only once

```console
bandit8@bandit:~$ head data.txt
s2ZGuAmX6cY1gJ9ER1qkXDCWTFntPJvJ
6hXvdZamDJFnfKX8O8UZPVjZpjeqeq6M
zJmXl1uLmwGC7r6mhGj1MJ0WEepnHSoT
RJizoPEBRhVuM5dF8NbRoUAcFgCYxAby
QrMLTTEu3KGuydS2w9FLTTLzuRldf6f6
B3E7u3CYUKsHrS3FL4OxwnQ8mV41JsmC
h44iM4fCazdJGlR3i4QGaSR6FtyGmd4Q
hisCIm8EcxJQhaaCxGZ5B02d2Pp8YFF2
0TTLuJ0jGXQM5Knk21Ghi4iisHYJOfzI
wN85lAbx5wkDs0IfVpbI1dSUSgY16Qml
bandit8@bandit:~$ sort data.txt | uniq -c | grep "1 "
      1 EN632PlfYiZbn3PhVK3XOGSlNInNE00t
```

__Flag:__ ```EN632PlfYiZbn3PhVK3XOGSlNInNE00t```

## Level 9 -> 10

The password for the next level is stored in the file __data.txt__ in one of the few human-readable strings, beginning with several ‘=’ characters.

```console
bandit9@bandit:~$ ls
data.txt
bandit9@bandit:~$ strings data.txt | head
;*1}Kf
z!d2
x0&h
=id6
[(V#
IkSR3(8|
11u"
Kw5-T
j6.4
w7+R
bandit9@bandit:~$ strings data.txt | grep ===
========== the
bu========== password
4iu========== is
========== G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
```

__Flag:__ ```G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s```

## Level 10 -> 11

The password for the next level is stored in the file __data.txt__, which contains base64 encoded data

```console
bandit10@bandit:~$ ls
data.txt
bandit10@bandit:~$ cat data.txt
VGhlIHBhc3N3b3JkIGlzIDZ6UGV6aUxkUjJSS05kTllGTmI2blZDS3pwaGxYSEJNCg==
bandit10@bandit:~$ cat data.txt  | base64 -d
The password is 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
```

__Flag:__ ```6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM```
