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

<p align="center"><img src="/images/0x01.jpg"></p>

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
