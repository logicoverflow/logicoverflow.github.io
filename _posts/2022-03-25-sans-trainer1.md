---
layout: single
title: "Trainer: Levels 0x01 - 0x09"
header:
  overlay_image: cyber-newlocks.jpg
  caption: "[__OverTheWire__](http://overthewire.org/wargames/bandit)"
---

<p align="center"><img src="/images/sans-new2cyber-logo.png"></p>

## 0x01 Level
__10 points (Linux)__

### Challenge

SSH to the linux trainer:

__trainer.threatsims.com__

Note: This is not a web based link, it's an SSH host and you can connect to it via SSH protocol with tool such as PuTTY (google), or in linux use the ssh command.

username: level0 password: level0

After logging in to level0 you will be looking for the password to level1.

The flag is always for the level in the challenge name. You will find it by completing the previous level.

The password will be the login to level1

Note: Not the standard flag format

author: [@nopresearcher](https://twitter.com/NopResearcher)

### Solution
The solution provided is done in linux with the ssh command. If you're using Windows, you'll want to use PuTTY or consider learning more about Windows Subsystem for Linux.

```console
┌──(logicoverflow㉿ALNLPTRV)-[~]
└─$ ssh level0@trainer.threatsims.com
The authenticity of host 'trainer.threatsims.com (147.182.253.159)' can't be established.
ED25519 key fingerprint is SHA256:k/h6wsNfQKieYuzuNJioOkTkFfzgn4ESQs42Zbvk5ug.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added 'trainer.threatsims.com' (ED25519) to the list of known hosts.
level0@trainer.threatsims.com's password:
Linux trainer 4.19.0-19-cloud-amd64 #1 SMP Debian 4.19.232-1 (2022-03-07) x86_64

The programs included with the Debian GNU/Linux system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Debian GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent
permitted by applicable law.
Last login: Thu Mar 24 20:16:43 2022 from 31.17.250.2

    ====================================================================
    ||                                                                ||
    ||     .--.          Welcom to the Linux Trainer!                 ||
    ||    | o_o|                                                      ||
    ||    | ==>|          To view the level instructions again        ||
    ||   / /   \ \         type: cat welcome_message                  ||
    ||  ( |     | )                                                   ||
    || /' |_____/'\       Getting Stuck? Need help with a level?      ||
    || \___)--(___/         type:  cat helpme                         ||
    ||                                                                ||
    ||                    Use "su - level#"  to change levels         ||
    ||                                                                ||
    ||                    feedback: nopresearcher@gmail.com           ||
    ||                                                                ||
    ||                                                                ||
    ====================================================================

Welcome to Level 0

The password for the next level is in this user's home directory

level0@trainer:~$ ls
hash.txt  hash.txt.save  helpme  level1_password  level1_password.save  welcome_message
level0@trainer:~$ cat level1_password
4202c26842398c1d0772ed9eed195113
```

__Flag:__ ```4202c26842398c1d0772ed9eed195113```

## 0x02 Level
__10 (Linux)__

### Challenge

The password to level

Note: Not the standard flag format

author: [@nopresearcher](https://twitter.com/NopResearcher)

### Solution

```console
Welcome to Level 1

The password for the next level is in this user's home directory, but you may have to dig a bit.

level1@trainer:~$ ls
helpme  some_directory  welcome_message

level1@trainer:~$ cd some_directory/

level1@trainer:~/some_directory$ ls
level2_password  level2_password.save  maybe

level1@trainer:~/some_directory$ cat level2_password
943430e07fd566bc96aa05fca3c96e48
```

__Flag:__ ```943430e07fd566bc96aa05fca3c96e48```
