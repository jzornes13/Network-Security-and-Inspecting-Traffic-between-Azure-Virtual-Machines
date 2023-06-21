# network-security-and-inspecting-traffic-between-azure-virtual-machines
<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. This repository is based on previous work done configuring active directory with azure. <br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- creating 2 virtual machines in azure, both using the same resource group
- windows 10 operating system
- linux ubuntu operating system
- using remote desktop (RDP) to install wireshark
- use wireshark and powershell to make observations( ssh, icmp, dns, http, https)
- how to display and flush our dns 

<h2>Actions and Observations</h2>
- log into Azure, there are a couple of ways to do everything in Azure, the header or center of the page click create virtual machine.
click Azure virtual machine (VM)
<p>
<img src="https://imgur.com/0QMrH4G.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
1
    
- name your VM anything you want in this case we named it VM1
  
- resource group is automatically given a name but you can change it.
- change the region to your own, we used west US 3
- choose the size of the server taking into account what you will be using it for. we chose Standard e2 v3- 2vcpus, 16 gib memory
- create a username and password (just remember your credentials!)
- make sure to check your box (bottom left)
- we can go ahead and skip everything else and click review/create
- if you get the go ahead in the form of "validation passed" click create and were good to go, let it set up your machine.

</p>
<br />

<p>
<img src="https://imgur.com/tbajTdo.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
2
-Repeat the same process for our 2nd vm but using Ubuntu for the operating system.
-again name it whatever you want.
-set the resource group to the same one created for the first virtual machine.
-keep the size of the vcpus the same as the first machine
    -also use the same location in the first one we used west US 3
Change authentication to "Password"
</p>
<br />

<p>
<img src="https://imgur.com/bC8VLA4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
3
-make sure the virtual network is the same as the first VM(windows OS)
-click review/create
-don't forget to click your accept box bottom left if need be or you will get a fail validation.
</p>
<br />

<p>
<img src="https://imgur.com/r4TS3cW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
4
Connecting to VM1 and installing wireshark
    
-in Azure go to vm1 and copy the public ip address(little button on the right side next to the numbers)
-press windows key button on your keyboard and type "remote desktop connection"(RDP)
-paste the ip address into the remote desktop and click connect
-enter user name and password(if it has a username already selected click "show option" and "other" to put in the right credentials as seen below.
-security prompt will pop up click yes
-you can disable all privacy settings when asked just turn everything off (not needed for these purposes)
-hit accept


</p>
<br />

<p>
<img src="https://imgur.com/HN4gsxY.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
5
</p>
<br />


<p>
<img src="https://imgur.com/mBrjWIk.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
6
-on vm1 go to whatever internet you have most likely Microsoft edge and search for wireshark
-select windows intel installer to start downloading
-click open file or you can go to your downloads file in file explorer.
-the install prompt will appear just keep hitting next until its done.
-agree with any prompts during this process, leave everything on defult, keep going to install button lights up.
-click install then finish
</p>
<br />


<p>
<img src="https://imgur.com/p1NaSZd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
7
</p>
<br />


<p>
<img src="https://imgur.com/sxB0uvi.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
8
Observe icmp traffic using wireshark

-inside vm1 run wireshark
-there will be a blue shark fin at the top that's the button to press to start capturing traffic
-you can see activity even though you aren't doing anything
</p>
<br />


<p>
<img src="https://imgur.com/KWvNRQB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
9
</p>
<br />


<p>
<img src="https://imgur.com/WkjTMFI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
10
</p>
<br />


<p>
<img src="https://imgur.com/04eQucd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
11
-go to the search box type in ICMP then enter.
    -you should see them all blank(no icmp activity)
</p>
<br />


<p>
<img src="https://imgur.com/L1ZHpav.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
12
-go to vm2 (Ubuntu) overview page in azure copy the private ip address (not the public)
-return to vm1 press the window button on your keyboard and type cmd or powershell
-type in Ping -t "private ip address" (the one you just copied)
-observe Wireshark packets being sent
</p>
<br />


<p>
<img src="https://imgur.com/4JuHFDT.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
13
While that is pinging we will try to deny them and see what happens

</p>
<br />

<p>
<img src="https://imgur.com/6oDy0jH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
13a
-in Azure type network security groups
-click vm2-nsg
-go to inbound rules
-click add
</p>
<br />


<p>
<img src="https://imgur.com/JkMAUeo.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
14
</p>
<br />


<p>
<img src="https://imgur.com/VzAGSag.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
14a
-change the protocol to icmp
-change the action to deny
-change the priority to lower than is already set( so it performs the task before any task above it)
-click add
-return to vm1 to observe the "timed out" status 
</p>
<br />


<p>
<img src="https://imgur.com/PHvGmuh.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
15
</p>
<br />


<p>
<img src="https://imgur.com/foxwdCs.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
16
</p>
<br />


<p>
<img src="https://imgur.com/rZcXE35.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
17
-we saw the denial of packets now lets switch it back but we don't have to delete it we can change action again to allow 
</p>
<br />


<p>
<img src="https://imgur.com/1D9ZOzL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
18
-once observed press control+c to stop the ping
</p>
<br />


<p>
<img src="https://imgur.com/zWHrP91.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
19
Observe SSH traffic using wireshark

-in wireshark type SSH or tcp.port==22(more direct) in the search bar and press enter(should be no activity)
</p>
<br />


<p>
<img src="https://imgur.com/1Ad5pSZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
20
-
</p>
<br />


<p>
<img src="https://imgur.com/I54EvBU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
21
</p>
<br />


<p>
<img src="https://imgur.com/t02LLtB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
22
</p>
<br />


<p>
<img src="https://imgur.com/1t7rI2j.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
23
</p>
<br />


<p>
<img src="https://imgur.com/XhDbWX9.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
24
</p>
<br />


<p>
<img src="https://imgur.com/cu03fdb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
25
</p>
<br />


<p>
<img src="https://imgur.com/Vm4swNY.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
26
</p>
<br />


<p>
<img src="https://imgur.com/NHpbsG5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
27
</p>
<br />


<p>
<img src="https://imgur.com/GDxmiwm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
28
</p>
<br />


<p>
<img src="https://imgur.com/jfCRovL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
29
</p>
<br />



