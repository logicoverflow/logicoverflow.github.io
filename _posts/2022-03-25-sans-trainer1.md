---
layout: single
title: "Trainer: Levels 0x01 - 0x09"
header:
  overlay_image: cyber-newlocks.jpg
  caption: "[__OverTheWire__](http://overthewire.org/wargames/bandit)"
---

<p align="center"><img src="/images/sans-new2cyber-logo.png"></p>

## 0x01 Level
10 points (Linux)

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
10 (Linux)

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

## 0x03 Level
10 (Linux)

### Challenge

The password to level

Note: Not the standard flag format

author: [@nopresearcher](https://twitter.com/NopResearcher)

### Solution

```console
Welcome to Level 2

The password for the next level is in this user's home directory, but you have to dig even deeper.

level2@trainer:~$ ls
dir  helpme  welcome_message

level2@trainer:~$ cd dir/another_dir/another_another_dir/some_directory/

level2@trainer:~/dir/another_dir/another_another_dir/some_directory$ ls
level3_password

level2@trainer:~/dir/another_dir/another_another_dir/some_directory$ cat level3_password
2cadca6148093c403d82396252b8c4db
```

The ability to tab to see the list and prepopulate the next directory helps save time from typing _cd directory_ over and over.

__Flag:__ ```2cadca6148093c403d82396252b8c4db```

## 0x04 Level
10 (Linux)

### Challenge

The password to level

Note: Not the standard flag format

author: [@nopresearcher](https://twitter.com/NopResearcher)

### Solution

```console
Welcome to Level 3

The password for the next level is in this user's home directory, but you might not see it at first.

type: man ls    read about files that start with a dot (.)

level3@trainer:~$ ls -la
total 176
-rw-r--r--  1 level3 level3  9957 Mar 23 21:09 ''$'\033'
drwxr-x---  6 level3 level3  4096 Mar 24 21:31  .
drwxr-xr-x 26 root   root    4096 Aug 22  2021  ..
-rw-r--r--  1 level3 level3  9756 Mar 23 20:17  -a
-rw-r--r--  1 level3 level3   220 Apr 18  2019  .bash_logout
-rw-r--r--  1 level3 level3  3526 Apr 18  2019  .bashrc
drwx------  3 level3 level3  4096 Feb  4 17:46  .config
drwx------  3 level3 level3  4096 Mar 24 14:21  .gnupg
-r--r-----  1 level3 level3   355 Aug 22  2021  helpme
-rw-------  1 level3 level3    33 Mar 24 00:07  .lesshst
-rw-r-----  1 level4 level3    34 Aug 22  2021  .level4_password
-rw-------  1 level3 level3 12288 Sep 15  2021  .level4_password.swp
drwxr-xr-x  3 level3 level3  4096 Sep 15  2021  .local
-rw-r--r--  1 level3 level3   807 Apr 18  2019  .profile
drwx------  2 level3 level3  4096 Feb  4 16:58  .ssh
-rwxr-xr-x  1 level3 level3 81512 Feb  4 18:29  tree
-rw-------  1 level3 level3  7897 Mar 24 21:31  .viminfo
-r--r-----  1 level3 level3   182 Aug 22  2021  welcome_message

level3@trainer:~$ cat .level4_password
72f6af6b0005adb15fbc91e1b140115f
```

__Flag:__ ```72f6af6b0005adb15fbc91e1b140115f```

## Ox05 Level
10 (Linux)

### Challenge

The password to level

Note: Not the standard flag format

author: [@nopresearcher](https://twitter.com/NopResearcher)

### Solution

```console
Welcome to Level 4

The password for the next level is in this user's home directory, just like the last levels you might have to dig.

type: man ls    read about files and folders that start with a dot (.)

level4@trainer:~$ ls -la
total 100
drwxr-x---  7 level4 level4 4096 Mar 24 17:08  .
drwxr-xr-x 26 root   root   4096 Aug 22  2021  ..
-rw-r--r--  1 level4 level4 9756 Mar 23 20:38  -a
-rw-r--r--  1 level4 level4  220 Apr 18  2019  .bash_logout
-rw-r--r--  1 level4 level4 3526 Apr 18  2019  .bashrc
drwx------  3 level4 level4 4096 Mar 24 14:24  .gnupg
-r--r-----  1 level4 level4  438 Aug 22  2021  helpme
drwx------  2 level4 level4 4096 Mar 24 19:28  .hidden_dir
drwxr-xr-x  3 level4 level4 4096 Sep 15  2021  .local
-rw-r--r--  1 level4 level4 9835 Nov 17 13:03 'ls - a'
-rw-r--r--  1 level4 level4 9835 Nov 17 13:05 'ls -a'
-rw-r--r--  1 level4 level4 9835 Nov 17 13:01  ls-a
-rw-r--r--  1 level4 level4  807 Apr 18  2019  .profile
drwx------  2 level4 level4 4096 Feb  4 17:02  .ssh
drwxr-xr-x  2 level4 level4 4096 Sep 15  2021  .vim
-rw-------  1 level4 level4 1762 Mar 24 17:08  .viminfo
-r--r-----  1 level4 level4  208 Aug 22  2021  welcome_message

level4@trainer:~$ cd .hidden_dir/

level4@trainer:~/.hidden_dir$ ls -la
total 28
drwx------ 2 level4 level4 4096 Mar 24 19:28  .
drwxr-x--- 7 level4 level4 4096 Mar 24 17:08  ..
-rw-r----- 1 level5 level4   34 Aug 22  2021  .level5_password
-rw-r--r-- 1 level4 level4 1024 Mar 24 19:28  ..level5_password.swp
-rw-r--r-- 1 level4 level4 9835 Nov 17 13:05 'ls -a'

level4@trainer:~/.hidden_dir$ cat .level5_password
7b6c2552940f47a27fbd729ae0e2893c
```

__Flag:__ ```7b6c2552940f47a27fbd729ae0e2893c```

## 0x06 Level
10 (Linux)

### Challenge

The password to level

Note: Not the standard flag format

author: [@nopresearcher](https://twitter.com/NopResearcher)

### Solution

```console
Welcome to Level 5

For this level the password is in level6's home directory.  Due to a persmissions error, the level5 user can access it.  Think about the directories you have already seen and what file name patterns.

level5@trainer:~$ ls
helpme  welcome_message

level5@trainer:~$ cd ..

level5@trainer:/home$ ls
level0  level10  level12  level14  level16  level18  level2   level21  level3  level5  level7  level9
level1  level11  level13  level15  level17  level19  level20  level22  level4  level6  level8  trainer

level5@trainer:/home$ cd level6

level5@trainer:/home/level6$ ls
dir1   dir14  dir19  dir23  dir28  dir32  dir37  dir41  dir46  dir50  helpme
dir10  dir15  dir2   dir24  dir29  dir33  dir38  dir42  dir47  dir6   level6_password
dir11  dir16  dir20  dir25  dir3   dir34  dir39  dir43  dir48  dir7   welcome_message
dir12  dir17  dir21  dir26  dir30  dir35  dir4   dir44  dir49  dir8
dir13  dir18  dir22  dir27  dir31  dir36  dir40  dir45  dir5   dir9

level5@trainer:/home/level6$ cat level6_password
7cb1963d316b9a302cf6c204d35b7302
```

__Flag:__ ```7cb1963d316b9a302cf6c204d35b7302```

## 0x07 Level
10 (Linux)

### Challenge

The password to level

Note: Not the standard flag format

author: [@nopresearcher](https://twitter.com/NopResearcher)

### Solution

```console
Welcome to Level 6

The password for the next level is in this user's home directory, however this time there are too many directories to manually dig through.  For this level you will need the find command and search for a file that has pass in the title.

type: man find    read searching for filenames

level6@trainer:~$ find . -name "*password*"
./dir13/subdir40/level7_password
./level6_password

level6@trainer:~$ cat dir13/subdir40/level7_password
The password for level7 is:

RG8geW91IGV2ZW4gbGlmdCBicm8g
```

__Flag:__ ```RG8geW91IGV2ZW4gbGlmdCBicm8g```

## 0x08 Level
10 (Linux)

### Challenge

The password to level

Note: Not the standard flag format

author: [@nopresearcher](https://twitter.com/NopResearcher)

### Solution

```console
Welcome to Level 7


The password for the next level is in the password_directory.  For this level though, all files are exactly the same size.  You should look through each file to find the one that contains the password.

Hint: look for password

type: man find
      man grep
      man xargs

level7@trainer:~$ ls
helpme  password_directory  welcome_message

level7@trainer:~$ cd password_directory/

level7@trainer:~/password_directory$ ls
level8_password1    level8_password24  level8_password4   level8_password55  level8_password70  level8_password86
level8_password10   level8_password25  level8_password40  level8_password56  level8_password71  level8_password87
level8_password100  level8_password26  level8_password41  level8_password57  level8_password72  level8_password88
level8_password11   level8_password27  level8_password42  level8_password58  level8_password73  level8_password89
level8_password12   level8_password28  level8_password43  level8_password59  level8_password74  level8_password9
level8_password13   level8_password29  level8_password44  level8_password6   level8_password75  level8_password90
level8_password14   level8_password3   level8_password45  level8_password60  level8_password76  level8_password91
level8_password15   level8_password30  level8_password46  level8_password61  level8_password77  level8_password92
level8_password16   level8_password31  level8_password47  level8_password62  level8_password78  level8_password93
level8_password17   level8_password32  level8_password48  level8_password63  level8_password79  level8_password94
level8_password18   level8_password33  level8_password49  level8_password64  level8_password8   level8_password95
level8_password19   level8_password34  level8_password5   level8_password65  level8_password80  level8_password96
level8_password2    level8_password35  level8_password50  level8_password66  level8_password81  level8_password97
level8_password20   level8_password36  level8_password51  level8_password67  level8_password82  level8_password98
level8_password21   level8_password37  level8_password52  level8_password68  level8_password83  level8_password99
level8_password22   level8_password38  level8_password53  level8_password69  level8_password84  xargs
level8_password23   level8_password39  level8_password54  level8_password7   level8_password85

level7@trainer:~/password_directory$ grep -ri "password" .
./level8_password68:The password for level8 is:

level7@trainer:~/password_directory$ cat level8_password68
The password for level8 is:

bGV0J3MgZmluZCBzb21ldGhpbmcg
```
__Flag:__ ```bGV0J3MgZmluZCBzb21ldGhpbmcg```

## 0x09 Level
10 (Linux)

### Challenge

The password to level

Note: Not the standard flag format

author: [@nopresearcher](https://twitter.com/NopResearcher)

### Solution

```console
Welcome to Level 8

For this level the password is in an executable hidden in one of these sub-directories.  When you run the executable it will print out the flag.  To run the executable type: ./executable

type: man find

After finding and executing the binary, you should try to run the command strings on the it and review the output.  type: strings <executable>

level8@trainer:~$ ls
checklist.chk  dir13  dir18  dir22  dir27  dir31  dir36  dir40  dir45  dir5   dir9
dir1           dir14  dir19  dir23  dir28  dir32  dir37  dir41  dir46  dir50  helpme
dir10          dir15  dir2   dir24  dir29  dir33  dir38  dir42  dir47  dir6   welcome_message
dir11          dir16  dir20  dir25  dir3   dir34  dir39  dir43  dir48  dir7
dir12          dir17  dir21  dir26  dir30  dir35  dir4   dir44  dir49  dir8

level8@trainer:~$ strings checklist.chk
14556e7c704da0db5d7e5ef967fcc5d9  ./welcome_message
1e35339f9660d94cf11f75c5e2753a9f  ./checklist.chk
9afa484b24898f294e70031c369156dc  ./helpme
695cb2c3531973a3204398dac538a6b0  ./.ssh/known_hosts
f2c04e38b770c6e3bd2f797cc93d811f  ./dir24/subdir13/level9_password
22bfb8c1dd94b5f3813a2b25da67463f  ./.bash_logout
ee35a240758f374832e809ae0ea4883a  ./.bashrc
c54f77d63cec0883f3caef6bf05523f0  ./.lesshst
4900e95d4a9cf68d7a87a63325250b62  ./.viminfo
f4e81ade7d6f9fb342541152d08e7a97  ./.profile

level8@trainer:~$ cd dir24/subdir13/

level8@trainer:~/dir24/subdir13$ ls
level9_password

level8@trainer:~/dir24/subdir13$ ./level9_password
The password is: 96ab15e954f1267ea04c35de2d771c2b
```

__Flag:__ ```96ab15e954f1267ea04c35de2d771c2b```

