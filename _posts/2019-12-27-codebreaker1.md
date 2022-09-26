---
layout: single
title: "NSA Codebreaker Challenge 2019 - Task 1"
header:
  overlay_image: cyber-newlocks.jpg
---

# Task 1 - It Begins!

<p align="center"><img src="/images/NSATask1.png"></p>

## Description

Last year I participated in the 2019 NSA Codebreaker Challenge, which was the first time for me to take part in the event. I thought it would be great to do a write-up on the parts I was able to complete when the challenge was active.

Taken from the NSA Codebreaker challenge’s site (https://codebreaker.ltsnet.net/), “**The NSA Codebreaker Challenge provides students with a hands-on opportunity to develop their reverse-engineering / low-level code analysis skills while working on a realistic problem set centered around the NSA’s mission.**”

Every year a challenge is created, based on a fictional story thoroughly thought out to provide context and substance to the task at hand, which may be similar to what the NSA experiences and what they may need their employees to do to obtain intelligence.

Story background as taken from their site:

**DISCLAIMER – The following is a FICTITIOUS story meant for providing realistic context for the Codebreaker Challenge and is not tied in any way to actual events.

Tech savvy terrorists have developed a new suite of communication tools to use for attack planning purposes. Their most recent creation — TerrorTime — is a secure mobile chat application that runs on Android devices. This program is of particular interest since recent intelligence suggests the majority of their communications are happening via this app. Your mission is to reverse-engineer and develop new exploitation capabilities to help discover and thwart future attacks before they happen. There are 7 tasks of increasing difficulty that you will be working through as part of this challenge. Ultimately, you will be developing capabilities that will enable the following:

Spoof TerrorTime messages
Masquerade (i.e., authenticate) as TerrorTime users without knowledge of their credentials
Decrypt TerrorTime chat messages

The first three tasks of the challenge will provide you with everything you need to install and run TerrorTime in an Android emulator. You will also discover account information for two TerrorTime users, which will enable you to send chat messages between the users by running the app in two emulators. Beginning with Task 4, the difficulty will increase significantly as you begin working towards the goals outlined above. We hope you enjoy the challenge!**

## Challenge & Write Up

<p align="center"><img src="/images/NSATask1.1.png"></p>

Task 1 Requirements:

* Obtain the APK's SHA256 hash
* Obtain the 2 client's registration data

We are given some information regarding the storyline and our needed involvement to keep things moving forward. Our objective is the task 1 requirements provided above using the file provided to us, which contains some captured traffic.

To view the information about the captured traffic, we will use a widely popular program called Wireshark. For those who are not familiar with Wireshark, it is a free and open-source packet analyzer used for network troubleshooting, analysis, software, and communications protocol development. After downloading the file and opening it in Wireshark, we are presented with thousands of packets. Immediately in green, I notice the terrortime.apk app was downloaded with the GET protocol, which could have been a wget, curl, or visit in a browser.

<p align="center"><img src="/images/NSATask1.2.png"></p>

You are able to extract objects from various types of traffic from HTTP using Wireshark, which is what we will do to obtain the APK file.

You need to go to ***File -> Export Objects -> HTTP...***

<p align="center"><img src="/images/NSATask1.3.png"></p>

You will find that there are two files available to download from the captured traffic. We know the APK file is needed in order to obtain the SHA256 hash, but we will download the other file as it may potentially contain valuable information to our mission.

The first requirement for the task is to obtain the hash of the APK. There are many different ways to do this, but we will use Kali Linux. For those not familiar with Kali Linux, it is an advanced Linux penetration testing platform. You can find more information about it here: https://www.kali.org/.

Using Kali’s built-in function, we will enter the following command ```sha256sum terrortime.apk``` and receive the hash:

```a166eaf4608e6755f604fdc0176d4e961e695862b45aee778aec20f305b637af```

<p align="center"><img src="/images/NSATask1.4.png"></p>

We have now completed 50% of task 1!

Next is for us to obtain the 2 client’s registration data. We do not really know where to go to find that data, but I do recall we downloaded two files… let’s take a look at that second file. Reviewing the file, we find that it contains the client ID and client secret for two users. This must be the last piece of information that we are looking for as both pieces form a type of authentication.

<p align="center"><img src="/images/NSATask1.5.png"></p>

We formulate the two pieces of data into two strings for submission

    Client 1: ```shira–vhost-245@terrortime.app:N1V2tYkXgQYofn```
    Client 2: ```zachary–vhost-245@terrortime.app:ny0agIcguv8F2Q```

With the requirements of Task 1 being met, we submit what we found and receive the following message:

<p align="center"><img src="/images/NSATask1.6.png"></p>

Next up, Task 2!
