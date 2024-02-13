<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />




<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, DHCP, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Create Resources in Azure
- Observe ICMP Traffic
- Observe SSH Traffic
- Observe DHCP Traffic
- Observe DNS Traffic

<h2>Actions and Observations</h2>

Create Resources in Azure


- Create a Windows 10 Virtual Machine in Azure.


![image](https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/2c346295-a218-46c8-84b2-4f7895f35ae2)


![image](https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/ff3e7501-29d9-407c-99b5-5c86a7460b27)


- Create a new resource group.
- Name this Virtual Machine VM-1.
- For the image choose Windows 10 Pro, version 22H2 - x64 Gen2 (free services eligible).


![image](https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/3c6d1af6-c28e-4729-8ffa-9d55e2c5cb3a)


- Create a username and password(don't forget your username and password!).


![image](https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/7bd25a1b-81c5-4b39-99e2-b2550f71b774)


- Wait for the validation process and hit create.


![image](https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/5b50a0ad-f173-4ed6-a57e-96e931617280)
