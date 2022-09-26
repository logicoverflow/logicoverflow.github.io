---
layout: single
title: "NSA Codebreaker Challenge 2019 - Task 3"
header:
  overlay_image: cyber-newlocks.jpg
---

# Task 3 - Turn of Events

<p align="center"><img src="/images/NSATask3.png"></p>

## Description

Last year I participated in the 2019 NSA Codebreaker Challenge, which was the first time for me to take part in the event. I thought it would be great to do a write-up on the parts I was able to complete when the challenge was active.

In the first task, we obtained the terrortime APK file, found its SHA256sum hash, and two client registration information for the app. In the second task, we obtained the app’s permissions, and learned some information regarding their certificate. We will now proceed with the third task for our continued mission against the terrorists.

## Challenge & Write Up

<p align="center"><img src="/images/NSATask3.1.png"></p>

Task 3 Requirements:

* IP address of the OAUTH server
* IP address of the XMPP server

We are given a database file in which the Analysts were able to recover and by analyzing it,  we are to obtain the authentication and chat servers used by the app.

As you’ll encounter with every problem, there are multiple ways to perform this task. Using Kali Linux, there are two easy ways to do this, one graphical (GUI) and the other via command-line. During the active challenge, I obtained the information via the command-line, which is what this guide will use.

To open the database file in question, we will use **SQLite3**, which is built-in with Kali Linux. The command to open start it, simply enough is ```sqlite3``` From here if you are not familiar with the proper switch commands, you can enter ```.help``` to provide you a list of options and its descriptions or use Google-Fu and find SQLite’s site: https://sqlite.org/cli.html.

Let us open the database by entering ```.open clientDB.db``` We will need to know what tables are in the database to help us analyze things further, so we enter ```.tables```. We learn that the database has 3 tables: **Clients**, **Contacts**, and **Messages**. To find how the table is structured, we need the layout, which is obtained by acquiring the schema. Since we have 3 tables, let us acquire the schema for each of them by entering ```.schema <tablename>``` (eg. .schema Clients).

* **Clients** – CREATE TABLE Clients(cid TEXT NOT NULL,rsip TEXT,xname TEXT,xsip TEXT,csecret BLOB,atok BLOB,rtok BLOB,asip TEXT,atokexp INTEGER,rtokexp INTEGER,pubkey BLOB,privkey BLOB,checkpin BLOB);
* **Contacts** – CREATE TABLE Contacts(contactid TEXT NOT NULL, cid TEXT NOT NULL );
* **Messages** – CREATE TABLE Messages(tstamp INTEGER, cid TEXT NOT NULL,contactid TEXT NOT NULL, fromclient INTEGER,msg BLOB );


<p align="center"><img src="/images/NSATask3.2.png"></p>

Great, we know the schema for each table! To see if any of those tables have any data, we will perform a SQL Query. To see the data for the **Clients** table, we enter ```SELECT * FROM Clients;```

We are presented with data from the table, which seems to be only one record.

<p align="center"><img src="/images/NSATask3.3.png"></p>

Reviewing the record, we find two addresses: **register.terrortime.app** and **chat.terrortime.app**, which corresponds to our request of the address for two servers. We need to obtain the IP address for each of those domains. You can easily do this by performing a ping against them. We enter ```ping register.terrortime.app``` and ```ping chat.terrortime.app```, and receive **54.197.185.236** , **51.91.5.130** respectively.

<p align="center"><img src="/images/NSATask3.4.png"></p>

Judging from their name, the register sub-domain must be the OAUTH (Open Authentication) server and the chat sub-domain must be the XMPP (Extensible Messaging and Presence Protocol) server.

* **IP Address of OAUTH Server**: ```54.197.185.236```
* **IP Address of XMPP Server**: ```51.91.5.130```

With the requirements of Task 3 being met, we submit what we found and receive the following message:

<p align="center"><img src="/images/NSATask3.5.png"></p>

With the completion of Task 3, I have reached as far as I have while the challenge was going on due to time constraints.
