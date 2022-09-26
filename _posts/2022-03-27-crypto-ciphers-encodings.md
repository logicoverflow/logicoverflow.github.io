---
layout: single
title: "SANS New2Cyber - Crypto, Ciphers, n Encodings"
header:
  overlay_image: cyber-newlocks.jpg
---

## Mind the Padding
10 (Crypto)

### Challenge

You'll need a pad for this one. Key is the most famous animal of 2020

ma{qmeg}

author: [@pwneip](https://twitter.com/pwnEIP)

### Solution

<p align="center"><img src="/images/pad1.png"></p>

Tool: [One Time Pad](http://rumkin.com/tools/cipher/otp.php)

<p align="center"><img src="/images/pad2.png"></p>

__Flag:__ ```ts{king}```

## Don't touch the third rail
10 (Crypto)

### Challenge

tiair}sZgzgCpeFW{yyhT

author: [@pwneip](https://twitter.com/pwnEIP)

### Solution

Tool: [CyberChef](https://gchq.github.io/CyberChef/#recipe=Rail_Fence_Cipher_Decode(3,0))

_Note: Hint is provided in the title, the third rail, which informs you of the cipher and offset needed._

<p align="center"><img src="/images/rail.png"></p>

__Flag:__ ```ts{ZigyzagyCipherFTW}```

## All about that base
10 (Crypto)

### Challenge

*dHN7SXNUaGlzRW5jcnlwdGlvbn0=*

author: [@pwneip](https://twitter.com/pwnEIP)

### Solution

Tool: [Cipher Identifier](https://www.dcode.fr/cipher-identifier)

<p align="center"><img src="/images/base1.png"></p>

Tool: [CyberChef](https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true))

<p align="center"><img src="/images/base2.png"></p>

__Flag:__ ```ts{IsThisEncryption}```

## All about that base remix
10 (Crypto)

### Challenge

*ORZXWVDINFZUS43UN52GC3DMPFCW4Y3SPFYHI2LPNYQX2===*

author: [@pwneip](https://twitter.com/pwnEIP)

### Solution

Tool: [Cipher Identifier](https://www.dcode.fr/cipher-identifier)

<p align="center"><img src="/images/baseremix1.png"></p>

**Tool**: [CyberChef](https://gchq.github.io/CyberChef/#recipe=From_Base32('A-Z2-7%3D',true))

<p align="center"><img src="/images/baseremix2.png"></p>

__Flag:__ ```ts{ThisIstotallyEncryption!}```

# Two Streams
10 (Crypto)

### Challenge

<p align="center"><img src="/images/streams.jpg"></p>

*tu{OtaOdadqtfNltQcsrsrVhbwYuiLopokb}*

author: [@pwneip](https://twitter.com/pwnEIP)

### Solution

Tool: [Cyber Chef](https://gchq.github.io/CyberChef/)

_Note: The title hints that this is a Bifid Cipher._

__Flag:__ ```ts{TwoStreamsAreBetterThanOneStream}```

## et tu brute
10 (Crypto)

### Challenge

*gf{NaByqvrOhgNTbbqvr}*

author: [@pwneip](https://twitter.com/pwnEIP)

### Solution

If you know your history, the title will inform you as to what type of cipher it is. If you're still unsure, you can proceed to use a Cipher Identifier.

Tool: [Cipher Identifier](https://www.dcode.fr/cipher-identifier)

<p align="center"><img src="/images/brutus1.png"></p>

Tool: [CyberChef](https://gchq.github.io/CyberChef/#recipe=ROT13(true,true,false,13))

<p align="center"><img src="/images/brutus2.png"></p>

__Flag:__ ```ts{AnOldieButAGoodie}```

## n Eggs
10 (Crypto)

### Challenge

*BAABA BAAAB AAAAB AAAAA AAABA ABBAB ABBAA ABAAA BAAAB ABABB BABBA ABBAA AAAAA ABABB AABAA*

author: [@pwneip](https://twitter.com/pwnEIP)

### Solution

Tool: [Cipher Identifier](https://www.dcode.fr/cipher-identifier)

<p align="center"><img src="/images/eggs1.png"></p>

Tool: [CyberChef](https://gchq.github.io/CyberChef/#recipe=Bacon_Cipher_Decode('Standard%20(I%3DJ%20and%20U%3DV)','0/1',false))

<p align="center"><img src="/images/eggs2.png"></p>

__Flag:__ ```TSBACONISMYNAME```

## AFSC 29331
10 (Crypto)

### Challenge

-.. .. - - -.--/-... --- .--. .--. . .-. ...

Note: Not the standard flag format

author: @pwneip

### Solution

Tool: [CyberChef](https://cyberchef.org/#recipe=From_Morse_Code('Space','Line%20feed'))

<p align="center"><img src="/images/afsc.png"></p>

__Flag:__ ```DITTOPPERS```

## Why are they even in that order in the first place?
10 (Crypto)

### Challenge

20:19:12:15:14:7:5:19:20:3:15:13:2:15:5:22:5:18:18:5:3:15:18:4:5:4

Note: Not the standard flag format

author: @pwneip

### Solution

Tool: [CyberChef](https://cyberchef.org/#recipe=A1Z26_Cipher_Decode('Colon'))

<p align="center"><img src="/images/order.png"></p>

__Flag:__ tslongestcomboeverrecorded