---
layout: single
title: "SANS New2Cyber - Ancient Crypto Corner"
header:
  overlay_image: cyber-newlocks.jpg
---

## Bacon for Breakfast
25 (Crypto)

### Challenge

Bacon’s cipher or the Baconian cipher is a method of steganography (a method of hiding a secret message as opposed to just a cipher) devised by Francis Bacon in 1605. A message is concealed in the presentation of text, rather than its content. The Baconian cipher is a substitution cipher in which each letter is replaced by a sequence of 5 characters.There are two versions of this cipher. We have collected a chart for one of them: [Download Here](https://github.com/logicoverflow/sans-new2cyber-ctf/blob/main/ancient-crypto-corner/bacon/bacon_table.png)

Can you decrypt the message below?

AABBB ABAAA AAABB AAABB AABAA ABBAB ABAAA ABBAB ABBBB ABABB AAAAA ABAAA ABBAB BAABA ABAAA AABBA AABBB BAABB

author: [@Rayhan0x01](https://twitter.com/rayhan0x01)

### Solution

**Tool**: [Baconian Cipher](https://www.dcode.fr/bacon-cipher)

A=A,B=B (αβ2)	HIDDENINPLAINSIGHT

__Flag:__ ```HIDDENINPLAINSIGHT```

## Rosicrucian Brotherhood
25 (Crypto)

### Challenge

Between 1614 and 1617, three anonymous manifestos were published, first in Germany and later throughout Europe. The manifestos caused excitement throughout Europe by declaring the existence of a secret brotherhood of alchemists and sages who were preparing to transform the arts and sciences, and religious, political, and intellectual landscapes of Europe. They released a cipher which is known to be a variation of the pigpen cipher. We have collected a chart that maps each symbol to a letter for this cipher : [Download Here](https://github.com/logicoverflow/sans-new2cyber-ctf/blob/main/ancient-crypto-corner/rosicrucian/rosicrucian_table.png)

Can you decrypt the message in this picture below?

[Download Link](https://github.com/logicoverflow/sans-new2cyber-ctf/blob/main/ancient-crypto-corner/rosicrucian/rosicrucian_enc.png)

author: [@Rayhan0x01](https://twitter.com/Rayhan0x01)

### Solution

**Tool**: [Rosicrucian Cipher](https://www.dcode.fr/rosicrucian-cipher)

__Flag:__ ```ANCIENTMYSTICALORDER```

## Order of the Temple
25 (Crypto)

### Challenge

The members of the Order of the Temple, a religious and military group from the Middle Ages were known as the Knights Templar. They invented a way to move money around safely. They kept the money in their castle, but gave the person a note to hand in at a castle in another country. The Knight there gave them money for the note. The Templars used encryption in their communications. The notes were therefore (possibly) encrypted so were useless if stolen. Only the Templar's could read them. We have collected a chart mapping each symbol to specific letter for this cipher : [Download Here](https://github.com/logicoverflow/sans-new2cyber-ctf/blob/main/ancient-crypto-corner/order/templar_table.png)

Can you decrypt the message in this picture below?

[Download Link](https://github.com/logicoverflow/sans-new2cyber-ctf/blob/main/ancient-crypto-corner/order/templar_inc.png)

author: [@Rayhan0x01](https://twitter.com/rayhan0x01)

### Solution

**Tool**: [Knights Templar Cipher](https://www.dcode.fr/templars-cipher)

__Flag:__ ```CIPHEROFWARRIORMONKS```

## Trithemius Ave Maria
25 (Crypto)

### Challenge

German abbot Johannes Trithemius was the author of the first printed book on cryptography but many thought his secret writings meant he was dabbling with the devil and he was forced to resign his post. One of his codes is known as the Ave Maria cipher. His book Polygraphiae consists of 384 columns of letters of the alphabet, each with a corresponding code word. We have collected a Page from this book published in 1518: [Download Here](https://github.com/logicoverflow/sans-new2cyber-ctf/blob/main/ancient-crypto-corner/trithemius/avemaria_table.jpg)

Can you decrypt the message below?

_Omnipotens redemptor_

_Dominus consolator_

_Clemens rex_

_Gloriosus confolator_

_Incompraehenfibilis deus_

_Gubernator optimus_

_fapientißimus clemens_

author: [@Rayhan0x01](https://twitter.com/rayhan0x01)

### Solution

**Tool**: [Trithemius Ave Maria](https://www.dcode.fr/trithemius-ave-maria)

__Flag:__ ```STEGANOGRAPHIA```

## Queen of Scots
25 (Crypto)

### Challenge

Mary, Queen of Scots (8 December 1542 – 8 February 1587), also known as Mary Stuart or Mary I of Scotland, reigned over Scotland from 14 December 1542 until her forced abdication on 24 July 1567. She was forced to renounce her throne in favour of her one-year-old son. After an unsuccessful attempt to regain the throne, she fled southward seeking the protection of her first cousin once removed Queen Elizabeth I of England. Mary had once claimed Elizabeth's throne as her own and was considered the legitimate sovereign of England by many English Catholics, including participants in a rebellion known as the Rising of the North. Perceiving Mary as a threat, Elizabeth had her confined in various castles and manor houses in the interior of England. Mary wanted to assassinate Queen Elizabeth I, and began exchanging messages with her co-conspirators, in particular Anthony Babington. This was dubbed the Babington Plot. Their messages were so treacherous that they were enciphered, so that they could not be read if they fell into the wrong hands. Mary's messages were captured by Elizabeth's spies and they were cracked by her chief codebreaker. Mary was immediately arrested, put on trial and the deciphered messages were used as evidence of her treachery. She was found guilty and was executed in 1587. Here is a chart of the symbols used in her cipher: [Download Here](https://github.com/logicoverflow/sans-new2cyber-ctf/blob/main/ancient-crypto-corner/queen/mary_table.png)

Can you decrypt the message in this picture below?

[Download Link](https://github.com/logicoverflow/sans-new2cyber-ctf/blob/main/ancient-crypto-corner/queen/mary_enc.png)

author: [@Rayhan0x01](https://twitter.com/rayhan0x01)

### Solution

**Tool**: [Mary Stuart Code](https://www.dcode.fr/mary-stuart-code)

__Flag:__ ```FREQUENCYANALYSISGOTME```

## The Name's Caesar
25 (Crypto)

### Challenge

Gaius Julius Caesar was a Roman general and statesman who played a critical role in the events that led to the demise of the Roman Republic and the rise of the Roman Empire. To protect messages of military significance, he used to write them in cipher, that is, by so changing the order of the letters of the alphabet, that not a word could be made out. If anyone wishes to decipher these, and get at their meaning, he must substitute the fourth letter of the alphabet, namely D, for A, and so with the others. Can you decrypt the message below?

fdhvdu_flskhu_vkliw_ri_wkuhh

author: [@Rayhan0x01](https://twitter.com/Rayhan0x01)

### Solution

**Tool**: [ROT Cipher](https://www.dcode.fr/rot-cipher) by 3

[A-Z]+3	caesar_cipher_shift_of_three

_Note_: Rotation ciphers are considered substitution ciphers. Furthermore, the Caesar cipher is actually a rotation of 13.

__Flag:__ ```caesar_cipher_shift_of_three```

