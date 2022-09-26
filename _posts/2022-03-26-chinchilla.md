---
layout: single
title: "SANS New2Cyber - Chinchilla Challenge"
header:
  overlay_image: cyber-newlocks.jpg
---

## 0x01 Cuzco's Great Adventure Flag
20 (Crypto)

### Challenge

Chinchilla Challenge: Cuzco’s Great Adventure

<p align="center"><img src="/images/0x01.jpg" width="300"></p>

Cuzco, the chinchilla, had always wanted to go on a grand adventure. She was boxed in, surrounded on all four sides by walls, but she was getting faster. If she could 10x (a term for upskilling a lot) her skills, continue her practice jumps and codebreaking, then maybe she could break through her walls, and get to that Parkour class she wanted to take.

Just out of her reach was a folded paper, which she thought might contain more Parkour info. One day she spotted a ciphered clue fluttering near a lock and she thought it might help her break through her gate.

Crack the following message to help Cuzco with flag 2. For flag 1, what method is used to obfuscate the message?

_Gb oernx guebhtu guvf jnyy lbh zhfg svaq guvf ybpx._

author: [@CarpeDiemT3ch](https://twitter.com/CarpeDiemT3ch)

### Solution

Tool: [Caesar Cipher](https://www.dcode.fr/caesar-cipher)

🠞13 (🠜13)	To break through this wall you must find this lock.

__Flag:__ ```Caesar Cipher```

## 0x02 Cuzco's Great Adventure Flag
20 (OSINT)

### Challenge

Using OSINT, help Cuzco find the name of the bridge (actual bridge name in French).

<p align="center"><img src="/images/0x021.jpg" width="400"></p>

author: [@CarpeDiemT3ch](https://twitter.com/CarpeDiemT3ch)

### Solution

Using the image provided, we'll utilize Google's Reverse Image Search at https://images.google.com

<p align="center"><img src="/images/0x022.png" width="600"></p>

The last search shows the name of the famous Lock Bridge in Paris, called The Pont des Arts.

__Flag:__ ```Pont des Arts```

## 0x03 Cuzco's  Great Adventure Flag
20 (Web)

### Challenge

Cuzco deciphered the code, broke open the lock, and was about to break through the barriers when she found another clue.

_U2VjdXJpdHkgdGhyb3VnaCBvYnNjdXJpdHkgY2FuIGFsc28gbWVhbiB0aGF0IGl0IGlzIGp1c3QgaGlkZGVuIGluIHRoZSBsYXllcnM=_

What is this encoded in?

author: [@CarpeDiemT3ch](https://twitter.com/CarpeDiemT3ch)

### Solution

Tool: [Cipher Identifier](https://www.dcode.fr/cipher-identifier)

Tool: [Base64 Converter](https://www.dcode.fr/base-64-encoding)

_Security through obscurity can also mean that it is just hidden in the layers_

__Flag:__ ```Base64```

## 0x04 Cuzco's Great Adventure Flag
20 (Stego, OSINT)

### Challenge

Flag 4 Use the image file to find the question:

<p align="center"><img src="/images/0x041.png" width="400"></p>

### Solution

Steganography portion:

```console
┌──(logicoverflow㉿ALNLPTRV)-[~]
└─$ strings believe_with_layers.png | grep FLAG
"FLAG 4 Question: Use OSINT, Who invented Parkour?"
"FLAG 5 Question: Use OSINT, What do you call someone who does Parkour?"
```

OSINT portion:

<p align="center"><img src="/images/0x04.png"></p>

__Flag:__ ```David Belle```

## 0x05 Cuzco's Great Adventure Flag
20 (Stego, OSINT)

### Challenge

Flag 5 Use the image file to find the question:

<p align="center"><img src="/images/0x041.png" width="400"></p>

### Solution

Steganography portion:

```console
┌──(logicoverflow㉿ALNLPTRV)-[~]
└─$ strings believe_with_layers.png | grep FLAG
"FLAG 4 Question: Use OSINT, Who invented Parkour?"
"FLAG 5 Question: Use OSINT, What do you call someone who does Parkour?"
```

OSINT portion:

<p align="center"><img src="/images/0x05.png"></p>

__Flag:__ ```traceur```

## 0x06 Cuzco's Great Adventure Flag
20 (OSINT)

### Challenge

Cuzco continued to learn more about Parkour; she was stronger, and she was ready to break through the barrier.

How will she do it? What will launch her from her perch in the comfy hammock? Sometimes it can be hard to make the decision to leave our comfort zone and risk the unknown - is it really worth it? But know this, there is a community here for you.

<p align="center"><img src="/images/0x061.png" width="300"></p>

Cuzco decided that she would brave it, even though there were risks, and that she would fail sometimes. Her risk profile adjusted for this and she wandered into the world to find her Parkour class and work on 10x her skills. She knew she’d need community, balance, and fortitude to help her, so she continued her quest to find these 3 things.

She grabbed the piece of paper as soon as she left her walls. She decided that for safekeeping, since she’s going on a quest, to digitize it so that then she can download it later.

On the quest…

First, she worked on developing her community. She’d been alone in her walls, but no chinchilla can do everything alone – she could not accomplish this quest as if she were an island. When she left she had to find others and decided to work with the squirrels. She worked on getting to know her new friends by studying them on YouTube.

She wanted to make meaningful connections and help their community too. Instead of clicking connect with the first squirrel she met, she tried to get to know something about each one and find ways to discuss their commonalities. That way she could write about this when she clicked connect if she was on TreeIn or Chitter. If she was in person she tried to connect with other squirrels based on shared interests.

Who made 2 YouTube videos about squirrel obstacle courses that Cuzco used to learn more about the squirrel community (1.0 and 2.0)?

author: [@CarpeDiemT3ch](https://twitter.com/CarpeDiemT3ch)

### Solution

<p align="center"><img src="/images/0x062.png"></p>

 __Flag:__ ```Mark Rober```

## 0x07 Cuzco's Great Adventure Flag
20 (OSINT)

### Challenge

<img src="https://github.com/logicoverflow/ctf/blob/main/sans-new2cyber-ctf/chinchilla/0x07/4mBfGxH.jpg" width="400" alt="Chinchilla leaning" />

She was starting to build a community. Next, she wanted to work on balance; both in the physical sense, as it is important for parkour and also in the sense of making sure that she wasn’t doing too many things.

She’d heard of PancakesCon and that it was a place where people celebrated knowledge of information security and having passions outside of cybersecurity. To learn more about this she listened to some talks from past years.

What was Shecky’s talk title from PancakesCon 2 in 2021 with the theme “We Persevere”?

author: [@CarpeDiemT3ch](https://twitter.com/CarpeDiemT3ch)

### Solution

<p align="center"><img src="/images/0x071.png"></p>

<p align="center"><img src="/images/0x072.png"></p>

__Flag:__ ```Avoiding Burnout, and Exciting Train Facts```

## 0x08 Cizco's Great Adventure Flag
20 (Web)

### Challenge

Cuzco was building her community, talking to others, getting known, making real connections with squirrel buddies, working on balance, and paying attention to her passion for other interests - for her, it was running, but she had one more thing to do: She needed to work on fortitude as she continued her quest to find her Parkour class. Many things in life are not easy and having strength can be helpful. There will be failure along the way. Comparing one’s journey to another person’s can be demoralizing and it is through having a good sense of community and goals that we can make progress. Cuzco knew these things. She practiced reflecting on the progress she’d made since she started her journey…she started with barriers and now there were fewer, she started with walls, and now she had a community, so she grew in her fortitude.

Now that Cuzco had strength from her community and some balance she could test her fortitude. She began work on the digitized file, which was the first thing she gathered on her trip.

Her new friends let her know that she should do some searching. So she opened Command Line (Terminal/Command Prompt/PowerShell) and decided to check the MD5sum of the file Parkour Flyer Information. She’d heard files could be tampered with and she wanted to make sure that hers was safe.

What is the MD5 checksum hash of the downloaded file <a href="/images/Parkour_Flyer_Information.pdf">Parkour Flyer Information</a>?

author: [@CarpeDiemT3ch](https://twitter.com/CarpeDiemT3ch)

###  Solution

```console
┌──(logicoverflow㉿kali)-[~/Downloads]
└─$ ls
Parkour_Flyer_Information.pdf
                                                                                                                                                        
┌──(logicoverflow㉿kali)-[~/Downloads]
└─$ md5sum Parkour_Flyer_Information.pdf 
9691c69c33f444222facf8fad310aca4  Parkour_Flyer_Information.pdf
```

__Flag:__ ```9691c69c33f444222facf8fad310aca4```

## 0x09 Cuzco's Great Adventure Flag
20 (Web)

### Challenge

Cuzco was aware that the file had information about Parkour that would help her learn even more, so she decided it was safe, downloaded it, and tried to open it. That’s when she learned the file had been encrypted. Can you help her crack the password?

She had one additional piece of information, this MD5 Hash:

_51F8571B1EC5D507670802B3A5F06B65_

author: [@CarpeDiemT3ch](https://twitter.com/CarpeDiemT3ch)

### Solution

```console
┌──(logicoverflow㉿kali)-[~/Downloads]
└─$ cat md5hash 
51F8571B1EC5D507670802B3A5F06B65

┌──(logicoverflow㉿kali)-[~/Downloads]
└─$ sudo hashcat -m 0 md5hash /usr/share/wordlists/rockyou.txt --force
[sudo] password for logicoverflow: 
hashcat (v6.2.5) starting

You have enabled --force to bypass dangerous warnings and errors!
This can hide serious problems and should only be done when debugging.
Do not report hashcat issues encountered when using --force.

OpenCL API (OpenCL 2.0 pocl 1.8  Linux, None+Asserts, RELOC, LLVM 11.1.0, SLEEF, POCL_DEBUG) - Platform #1 [The pocl project]
=============================================================================================================================
* Device #1: pthread-0x000, 1439/2942 MB (512 MB allocatable), 2MCU

Minimum password length supported by kernel: 0
Maximum password length supported by kernel: 256

Hashes: 1 digests; 1 unique digests, 1 unique salts
Bitmaps: 16 bits, 65536 entries, 0x0000ffff mask, 262144 bytes, 5/13 rotates
Rules: 1

Optimizers applied:
* Zero-Byte
* Early-Skip
* Not-Salted
* Not-Iterated
* Single-Hash
* Single-Salt
* Raw-Hash

ATTENTION! Pure (unoptimized) backend kernels selected.
Pure kernels can crack longer passwords, but drastically reduce performance.
If you want to switch to optimized kernels, append -O to your commandline.
See the above message to find out about the exact limits.

Watchdog: Temperature abort trigger set to 90c

Host memory required for this attack: 0 MB

Dictionary cache built:
* Filename..: /usr/share/wordlists/rockyou.txt
* Passwords.: 14344392
* Bytes.....: 139921507
* Keyspace..: 14344385
* Runtime...: 1 sec

51f8571b1ec5d507670802b3a5f06b65:Parkour                  
                                                          
Session..........: hashcat
Status...........: Cracked
Hash.Mode........: 0 (MD5)
Hash.Target......: 51f8571b1ec5d507670802b3a5f06b65
Time.Started.....: Sat Mar 26 22:34:24 2022, (0 secs)
Time.Estimated...: Sat Mar 26 22:34:24 2022, (0 secs)
Kernel.Feature...: Pure Kernel
Guess.Base.......: File (/usr/share/wordlists/rockyou.txt)
Guess.Queue......: 1/1 (100.00%)
Speed.#1.........:  2512.1 kH/s (0.07ms) @ Accel:256 Loops:1 Thr:1 Vec:4
Recovered........: 1/1 (100.00%) Digests
Progress.........: 437760/14344385 (3.05%)
Rejected.........: 0/437760 (0.00%)
Restore.Point....: 437248/14344385 (3.05%)
Restore.Sub.#1...: Salt:0 Amplifier:0-1 Iteration:0-1
Candidate.Engine.: Device Generator
Candidates.#1....: STAR22 -> PHOTO
Hardware.Mon.#1..: Util: 42%

Started: Sat Mar 26 22:34:22 2022
Stopped: Sat Mar 26 22:34:26 2022
```

__Flag:__ ```Parkour```

## 0x0A Cuzco's Great Adventure Flag
20 (Web)

### Challenge

Now that you’ve helped her open and view the file, Cuzco knows two things. One, the file creator should work on password complexity. Two, before visiting the website on the flyer, she should investigate it using some threat hunter sites. Investigate the site with the following tools:

Use <a href="https://www.whois.com/">https://www.whois.com/</a> or the whois command on the command line

URLscanner <a href="https://urlscan.io/">https://urlscan.io/</a> make sure it is a private scan

Pulsedive at <a href="https://pulsedive.com/">https://pulsedive.com/</a> and complete a passive scan of the site

Based on your research, what year was this site first registered?

Also, what level of risk would Cuzco be taking on if she were to visit the site?

Flag format: YEAR___*** The format will be YEAR_Case_Sensitive_Answer

It should be the 4 digit year_ and then 3 words

Cuzco had traveled far, met new friends, worked on balance, gained new knowledge, and gained 10 flags - effectively working on 10x her skills. She knew that eventually, she’d need to go back 127.0.0.1 (an IP address for localhost usually meaning you are home), and she had gained so much on her quest.

She decided to review a few resources to make her trip home a learning experience and have some balance too:

<a href="https://www.sans.org/blog/dont-miss-these-top-rated-sans-summit-replays/">https://www.sans.org/blog/dont-miss-these-top-rated-sans-summit-replays/</a>

<a href="https://www.sans.org/blog/visual-summary-of-sans-new-to-cyber-summit/">https://www.sans.org/blog/visual-summary-of-sans-new-to-cyber-summit/</a>

<a href="https://wakelet.com/wake/ZoDim7iESNHwLFr4DJeOC">https://wakelet.com/wake/ZoDim7iESNHwLFr4DJeOC</a>

And because balance:

<a href="https://youtu.be/VZrDxD0Za9I?list=PLu4wnki9NI_8VmJ7Qz_byhKwCquXcy6u9">https://youtu.be/VZrDxD0Za9I?list=PLu4wnki9NI_8VmJ7Qz_byhKwCquXcy6u9</a>

<a href="https://youtu.be/f0RQ5C7g_tA?list=PLnzLfzo-SovQvT8zbcBdkeNkwZ38f2SAM">https://youtu.be/f0RQ5C7g_tA?list=PLnzLfzo-SovQvT8zbcBdkeNkwZ38f2SAM</a>

She safely made it back to her 127.0.0.1, and once she arrived, she found that her home was more open than she remembered. There was more community surrounding it than she thought. She just had to look out the window and remember she’d had her adventure, there was help to be found, and she was part of this community - she belonged! Remember you belong here and are part of our community too.

author: [@CarpeDiemT3ch](https://twitter.com/CarpeDiemT3ch)

### Solution

<p align="center"><img src="/images/0x0A.png"></p>

__Flag:__ ```2002_very_low_risk```
