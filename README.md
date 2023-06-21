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
    -windows 10 operating system
    -linux ubuntu operating system
- using remote desktop (RDP) to install wireshark
- use wireshark and powershell to make observations( ssh, icmp, dns, http, https)
- hot to display and flush our dns 

<h2>Actions and Observations</h2>
second text
<p>
<img src="https://imgur.com/0QMrH4G.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
1
</p>
<br />

<p>
<img src="https://imgur.com/tbajTdo.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
2
</p>
<br />

<p>
<img src="https://imgur.com/bC8VLA4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
3
</p>
<br />

<p>
<img src="https://imgur.com/r4TS3cW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
4
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
</p>
<br />


<p>
<img src="https://imgur.com/L1ZHpav.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
12
</p>
<br />


<p>
<img src="https://imgur.com/4JuHFDT.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
13
</p>
<br />

<p>
<img src="https://imgur.com/6oDy0jH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
13a
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
</p>
<br />


<p>
<img src="https://imgur.com/1D9ZOzL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
18
</p>
<br />


<p>
<img src="https://imgur.com/zWHrP91.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
19
</p>
<br />


<p>
<img src="https://imgur.com/1Ad5pSZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
20
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



