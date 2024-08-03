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

Under the description tab, there is the Login information to the Kali VM.

![chrome_rjlL78DNXE](https://github.com/user-attachments/assets/195ab416-d147-46c0-89fb-f738237e61b2)

The next step is to download and import the 2 pre-built FTP VM's into Virtualbox. Unfortunatly, I was unable to link those files into this project.

After I downlaoded the 2 FTP VM's, I then went into the network settings of both to enable Network Adapter and change the network to Host-only Adapter

![chrome_9cYzObhFDt](https://github.com/user-attachments/assets/54901978-5241-476b-aa15-b1f3d6f17ab3)

![chrome_MY13viedJl](https://github.com/user-attachments/assets/bcf66f4b-17fd-495b-8091-9f398c9d7df1)

A very important note, for the lab to work, all three VM's must be on the same exact network. For me, I made sure both FTP VM's were on the VirtualBox Host-Only Ethernet Adapter #3 which is the one my original Kali VM is on. 

After starting both FTP VM's, I went to the FTP server VM first and went into Command Prompt and typed, ipconfig /renew. I am doing this just to make sure everything is clear and good to go with the IP Address. 

![chrome_AfZBFPv4Z9](https://github.com/user-attachments/assets/c50be41f-7205-4491-bc1c-736c441b3a66)

I will now do the same action with the FTP client VM.

![chrome_cbpzzbDpcn](https://github.com/user-attachments/assets/c566acaf-0693-407a-99ba-9e7cbc4600d8)


Important note, the client VM can ping the server, but the server VM cannot ping the client. The reason is that the ICMP firewall is not open on the CLient, only on the Server. 

The Ip Address on the FTP Client VM was 192.168.15.11 and for the Server VM, it was 192.168.15.12. This is very important.

Now lets ping the FTP server VM from the Client.

![chrome_TsiGg37P22](https://github.com/user-attachments/assets/724c1db3-4f89-45a3-9e76-ecef3ccbfdf3)

The ping was successful indicating the FTP VM's can communicate with each other. Now we need to make the Kali VM able to communicate as well.

To do this, I will run the ifconfig command in terminal to make sure there is no IP Address conflict.

![chrome_7SwY9vDI3Q](https://github.com/user-attachments/assets/7a1b065d-8350-4b2b-8151-bdf919e432ba)

The IP Address assosiated with this VM is 192.168.15.10, indicating there is no IP conflict.

Next, I will ping the FTP server VM to make sure the Kali VM is able to communicate.

![chrome_k8ttPAT8M7](https://github.com/user-attachments/assets/965c4361-4df1-4f33-b0eb-380a3e1bd6c0)

The ping was successful so now I will go to the FTP client VM and go to FileZilla. Click file and then site manager. In site manager, I willnow change the IP Address to 192.168.15.12, which is the IP of the Server VM. Once that is done, I will hit connect.

![chrome_aZkeiXFSw9](https://github.com/user-attachments/assets/872a059c-5b63-4629-a621-f0b117628dac)

![chrome_NqxAvyQB5f](https://github.com/user-attachments/assets/76885414-7bab-420f-8c30-268a3d3b25fc)

The purpose of this was to verify that communication has been successfully established between the CLient and Server VM. 
































