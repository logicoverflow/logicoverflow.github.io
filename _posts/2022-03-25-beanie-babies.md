---
layout: single
title: "Beanie Babies"
header:
  overlay_image: cyber-newlocks.jpg
---

## 0x01 Beanie Baby Collection
100 (web)

### Challenge

We heard sql injection can give you shell but we don't believe it. Anyways, we have a huge collection of beanie baby here: http://bb.threatsims.com:8084/

The flag format is unique

author: [@pwnEIP](https://twitter.com/pwnEIP)

### Hints/Solution

* SQLMap is a good tool to automate SQL injection!
* Video walkthrough : https://www.youtube.com/watch?v=B59tT9ehUI4

## 0x02 Beanie Baby Flagbearer
100 (web)

### Challenge

Look around the file system for credz.

author: [@pwnEIP](https://twitter.com/pwnEIP)

### Hints/Solution

* Find the password.bak file and bruteforce the file. The creds will give access to user account on the box
* Video walkthrough : https://www.youtube.com/watch?v=mdGOs473LcQ

## 0x03 Beanie Baby Flagholder
100 (web)

### Challenge

Look around the file system for credz.

author: [@pwnEIP](https://twitter.com/pwnEIP)

### Hints/Solution

* Find the password.bak file and bruteforce the file. The creds will give access to user account on the box. you can't drop into a shell but you can use: su username -c 'command here'
* Video walkthrough : https://www.youtube.com/watch?v=mdGOs473LcQ

## 0x04 Beanie Baby SQL DB
100 (web)

### Challenge

There is a flag in the beanies database, find it.

author: [@pwnEIP](https://twitter.com/pwnEIP)

### Hints/Solution

* Dump and grep flag pattern from beanies database.
* Video walkthrough : https://www.youtube.com/watch?v=OMAM5zsHSn8

## 0x05 Beanie Baby SQL DB 2
150 (web)

### Challenge

There is another flag in mysql, find it.

author: [@pwnEIP](https://twitter.com/pwnEIP)

### Hints/Solution

* Dump and grep flag format from beanies database.
* Video walkthrough : https://www.youtube.com/watch?v=xQHUohVuCbM
