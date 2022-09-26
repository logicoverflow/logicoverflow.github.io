---
layout: single
title: "DEFCON RTV 2020 - OSINT 2"
header:
  overlay_image: cyber-newlocks.jpg
---

We have completed the entire Logs section for the CTF event, let’s move over to Tunneler. For this section, there will only be three tasks as that was all I was able to complete due to various time constraints.

Let’s get started!

## First Task

<p align="center"><img src="/images/TLR-Bastion.png"></p>

It seems that we’ll be doing some SSH work for this series. For this task, we’re asked to connect to the bastion host with the information provided. I assume that means the flag must sit somewhere on the welcome message or home directory as no further details were given.

<p align="center"><img src="/images/TLR-Bastion-2.png"></p>

We need to SSH to the server, and in our case, I chose the last host listed in order to prevent from being overcrowded. So we used the __ssh__ command with the *username@hostname -p [port number]*. We are doing this via Kali Linux, if you’re using Windows, you’ll most likely be using PuTTy. If you’re in the latter, consider downloading and installing the Windows Linux Sub-System. It’s a great way to get a Linux shell on a windows computer to do whatever you need. Furthermore, you even get to choose what Linux operating system you want the shell to be, whether Kali, Ubuntu, or others.

<p align="center"><img src="/images/TLR-Bastion-3.png"></p>

We have successfully logged into the server and we’re presented with a welcome message. We’re given some information on bastion hosts and those related to our upcoming tasks. Finally, we’re also given our flag!

__Flag:__ ```ts{SSHtoANonStandardPort}```

## Second Task

<p align="center"><img src="/images/TLR-Browsing-Websites.png"></p>

For this task, we’re asked to browse a given IP address. As the previous task has some information for the future tasks, let’s review it to see what exact they’re asking us to do.

<p align="center"><img src="/images/TLR-Bastion-3.png"></p>

Reviewing this once more, it seems our objective is to forward a port or forward a tunnel to view a web server on an internal network. So what this means is that simply entering the IP address given into a browser won’t work as that address is an internal. For those who may not be quite familiar with networking or need a refresher, anytime you see an IP address starting with 10.x.x.x, it indicates it’s generally an internal Class A network.

<p align="center"><img src="/images/TLR-Browsing-Websites-2.png"></p>

We’re going to use SSH local port forwarding to complete this task. The -L indicates that this is a local forward to be done on port 8888. The following IP address and it’s port is what we’re looking to forward to, in this case, the web server. The last portion is the bastion server which has network access to communicate with the targeted web server.

<p align="center"><img src="/images/TLR-Bastion-3.png"></p>

After running the command and logging in we’re going to shown the same screen as we had previously. You may think immediately, okay, this did not work… However, don’t jump to that thought. We established the connection needed so we can have the local port forwarding occur. Remember, this is a local port forwarding, involving our local host on the port 8888.

<p align="center"><img src="/images/TLR-Browsing-Websites-3.png"></p>

So we head over to our browser, enter the local host, which is 127.0.0.1 along with the port we entered 8888. After submitting it, we’re taken to the page we our desired page, which is the web server and given our flag!

__Flag:__ ```ts{TheFirstTunnelIsTheEasiest}```

## Third Task

<p align="center"><img src="/images/TLR-SSH-in-Tunnels.png"></p>

For this task, it seems we’re being asked connect to the pivot host server through the initial bastion that we’ve connected to from the first task.

<p align="center"><img src="/images/TLR-Bastion-3.png"></p>

Connecting to the initial bastion once again, let’s see if any more information is given that may help us complete this task. In this case, the information shown here is nearly the same as what we’re told in the task itself.

Let’s review the information we know so far in its totality. 1) We know the initial server details and how to connect to it. 2) We know the details for the pivot host server we need to connect to. 3) This is an SSH challenge series, so we’ll have to use SSH in some way to complete this task.

*./ssh -L 22:164.90.147.46:2222 whistler@10.218.176.199*

Trying to use the command above without the ./ will inform you that you do not have permissions as it is attempting to reference what’s in the /usr/bin/ directory. However, if you do the ./, you’re referencing the copy of ssh stored in the home directory and that you want to run it. Apologizes that I do not have any screenshots for this as they were accidentally deleted when I was trying to consolidate everything into one document.

So what we’re doing here is using the copy of ssh found in our home directory on the bastion server, referencing a local port forward over port 22 (standard ssh port), the IP address and port of the bastion server, and the username@hostname of the pivot host server.

<p align="center"><img src="/images/TLR-SSH-in-Tunnels-2.png"></p>

We successfully connect to the pivot host server. No welcome message was displayed, but reviewing what is in the home directory, we see that one does exist. We use cat to display it and obtain our flag, along with more information for the upcoming tasks.

__Flag:__ ```ts{IThoughtWeLostYouOnTheWay}```

This wraps up what I’ve completed for this series.