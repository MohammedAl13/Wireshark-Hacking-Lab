# Wireshark-Hacking-Lab

In this project, we will create a Kali Linux virtual machine (VM) alongside two pre-built FTP VMs within VirtualBox to create a controlled hacking environment. We will intercept and analyze packets transmitted between the FTP VMs using Wireshark. The network packets will be files and login information shared between the VMs. Utilizing Wireshark packet capture capabilities no logs nor traceable events will be generated, ensuring that the capture remains undetected. This project aims to explore Wireshark's capabilities in network traffic analysis and evaluate its effectiveness in identifying security vulnerabilities and enhancing network defenses. Also, we will discuss some best practices to protect your organization's information from being easily stolen by Packet Sniffers such as Wireshark at the end.

This Hacking Lab will consist of the following components:
- Oracle Virtual Box
- Kali Linux VM
- 2 ftp pre-built VMs

***This home lab can be done for free. Unfortunatley, the files needed for this project are too large to link into this project and I have tried other methods of importing the files but methods have unfortunately failed. This lab will just be a walkthrough of what I did.***

Before starting, we must download and set up a virtual box. This is very straightforward, so I will not provide a step-by-step guide. If you need assistance, simply watch a short tutorial on YouTube on how to do so. Just ensure it is from Oracle and adjust whatever you need to to meet your computer's standards.

Once the Virtual Box is set up, we can download and create our Kali Linux VM.

Head on over to Virtualbox and at the top, select file, and select import new appliance. Select the Kali Linux ova file and adjust the CPU and RAM as per your need. I did not adjust the setting and went with 2 cpu's and 2048 MB of RAM. Once this is complete, click import.


