---
layout: single
title: "NSA Codebreaker Challenge 2019 - Task 2"
header:
  overlay_image: cyber-newlocks.jpg
---

# Task 2 - Permissions

<p align="center"><img src="/images/NSATask2.png"></p>

## Description

Last year I participated in the 2019 NSA Codebreaker Challenge, which was the first time for me to take part in the event. I thought it would be great to do a write-up on the parts I was able to complete when the challenge was active.

In the first task, we obtained the terrortime APK file, found its SHA256sum hash, and two client registration information for the app. We’ll now proceed with the second task for our continued mission against the terrorists.

## Challenge & Write Up

<p align="center"><img src="/images/NSATask2.1.png"></p>

Task 2 Requirements:

* List of App Permissions
* The SHA256 Hash of the Code Signing Certificate
* The Common Name of the Certificate Signer

If you recall from the previous challenge, we have the terrortime app from the first task. Our first goal is to find the app permissions, and there are multiple ways to go about this. Though an APK file is an installer on an Android device, it also is a zip file. One mention is to unzip the file and search for any files that may show us the permissions for the app. Another method, which is to use a free tool called **apktool**, which can be used in the reverse-engineering process for an app. It should be noted that **apktool** is not built-in with Kali Linux and will have to be installed via ```apt install apktool```.

In Kali Linux, we will run the command ```apktool d terrortime.apk```. This command will decompress the files and extract them into a different format.

<p align="center"><img src="/images/NSATask2.2.png"></p>

After we go into the newly created directory, we find two files and several folders. Let’s take a look at the first file called **AndroidManifest.xml**.

<p align="center"><img src="/images/NSATask2.3.png"></p>

When reviewing the file, we find there are two entries specifically labeled as permission near the top of the file. The two permissions are ```INTERNET``` and ```ACCESS_NETWORK_STATE```, and we now have completed 33.3% of the task.

Our task requires to obtain the SHA256 has of the Code Signing Certificate. As with before, there are many different ways to go about this, during the challenge I used **jadx-gui** (https://github.com/skylot/jadx).  I was able to convert the APK file into java files, which also had information about the certificate used. Though we will most likely need to view those files at a later date, I will be using **apksigner** in Kali Linux. It should be noted that **apksigner** is not built-in with Kali Linux and will have to be installed via ```apt install apksigner```.

In Kali Linux, we will run the command ```apksigner verify –print-certs terrortime.apk``` and receive some information regarding the certificate.

* If you’re new to Linux, the help menu might appear as if it doesn’t provide much information. However, you just may need to check the sub-help menu for the module or switch being used. For example, apksigner verify –help will give you the additional options to be used with the verify module/switch. You can also resort to using the internet and finding all you need here: https://developer.android.com/studio/command-line/apksigner.

<p align="center"><img src="/images/NSATask2.4.png"></p>

You will notice we are given the SHA-256 digest, which is the hash we are looking for ```32520bd39add77a5db82ec65564c3bb24f0ea327d817faeea7145d3f051efbc6```. Furthermore, you will find a line which as **CN=**, that CN is an abbreviation for **Common Name**, which in this case is ```dev_terrorTime_861561```. We now have obtained the remaining 66.6% of the requirements for the task.

With the requirements of Task 2 being met, we submit what we found and receive the following message:

<p align="center"><img src="/images/NSATask2.5.png"></p>

Next up, Task 3!
