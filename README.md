<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark and experiment with Network Security Groups. <br />




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

<h2>Create Resources in Azure</h2>


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


- Whenever you create a new VM in Azure, a virtual network is automatically made for you.


![image](https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/fa78d92f-af13-4f7f-b004-a15a086a0a5f)


- Create another VM and name it VM-2
- While creating VM2, select the previously created Resource Group and Vnet
- Create a Linux (Ubuntu)
- Make the same username and password as VM-1.


![image](https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/bdbc0791-e4f7-499a-a5c7-c433d2c1346d)






![image](https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/af758ccf-ca0d-4904-93d8-ea28492bf814)


- In the network tab choose the same Virtual Network as VM-1( if you don't see VM-1 network check to see if VM-1 is done being created).


![image](https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/9fd0cfa0-ed03-4e3f-a16d-7f63685dc295)


- Review/Create
- Go back to Virtual Machines to view your VMs.


![image](https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/bed7aa49-decc-4dfb-bc99-00d55ffdd005)


<h2>Observe ICMP Traffic</h2>
<p

</p>

- Log into VM-1 using a remote desktop or if on Mac OS download the Microsoft Remote Desktop app.
- Download Wireshark on VM-1.


![image](https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/fe633afa-84bc-4250-81a4-98e5fd6acf84)


![image](https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/bdd86e1f-a03c-4af6-a05b-cc6b2bfaf0d8)


![image](https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/160d5deb-76f6-4cce-8a11-b7816c270ea2)


![image](https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/229e1412-5a46-43f8-9bcf-dcffaac290dc)


![image](https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/270b302b-3155-4676-bd65-09abcc6960fd)


![image](https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/7dfd5e86-9db4-446a-95cd-c19b4178730e)
