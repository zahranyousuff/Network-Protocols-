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


<img height="70%" width="70%" alt="vm create" src="https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/019221e3-cca9-40bf-a7e4-003612e0d56d">


![image](https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/ff3e7501-29d9-407c-99b5-5c86a7460b27)


- Create a new resource group.
- Name this Virtual Machine VM-1.
- For the image choose Windows 10 Pro, version 22H2 - x64 Gen2 (free services eligible).


<img height="70%" width="70%" alt="vm1 create" src="https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/0ca41257-3539-4913-9be9-5cd28d00b7c5">


- Create a username and password(don't forget your username and password!).


<img height="70%" width="70%" alt="Screenshot 2024-02-12 at 1 03 29 PM" src="https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/1c6227a4-efc1-4794-ba14-c82426c4b0c6">


- Wait for the validation process and hit create.


<img height="70%" width="70%" alt="Screenshot 2024-02-12 at 1 06 38 PM" src="https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/242a7eef-3f96-4bd4-b1cc-c543f8368714">



- Whenever you create a new VM in Azure, a virtual network is automatically made for you.


<img height="70%" width="70%" alt="Screenshot 2024-02-12 at 1 09 34 PM" src="https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/c5cfdec6-d1a6-472b-bc35-1057f2935f48">



- Create another VM and name it VM-2
- While creating VM2, select the previously created Resource Group and Vnet
- Create a Linux (Ubuntu)
- Make the same username and password as VM-1.


<img height="70%" width="70%" alt="vm2 creat1" src="https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/71dc853f-d704-4107-bb28-0214af87c19a">


<img height="70%" width="70%" alt="vm2 create2" src="https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/8539bdf1-edcd-4878-bc40-b8516065de9e">






- In the network tab choose the same Virtual Network as VM-1( if you don't see VM-1 network check to see if VM-1 is done being created).


<img height="70%" width="70%" alt="Screenshot 2024-02-12 at 1 33 50 PM" src="https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/012b009c-a21d-416d-b53b-7b0266a5947d">



- Review/Create
- Go back to Virtual Machines to view your VMs.

<img height="70%" width="70%" alt="Screenshot 2024-02-12 at 1 37 01 PM" src="https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/53250648-eb7c-48eb-a355-44203a31b69d">


<h2>Observe ICMP Traffic</h2>
<p

</p>

- Log into VM-1 using a remote desktop or if on Mac OS download the Microsoft Remote Desktop app.
- Download Wireshark on VM-1.


<img height="70%" width="70%" alt="Screenshot 2024-02-12 at 8 02 54 PM" src="https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/08288f96-ff7d-4ddb-b2ab-36cb1d95df89">




<img height="70%" width="70%" alt="wireshark search" src="https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/dcfb0246-ad82-4b11-ade7-e22852b4896c">



<img height="70%" width="70%" alt="wireshark download page" src="https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/c039c627-52a8-4b55-aa0b-6e81f208942f">


<img height="70%" width="70%" alt="Screenshot 2024-02-12 at 1 55 16 PM" src="https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/99c91abc-69f5-43fb-8ed0-adfe242e00b2">



<img height="70%" width="70%" alt="Screenshot 2024-02-12 at 1 59 26 PM" src="https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/5865c3ce-a03f-4bef-b7ef-a78527b5999e">



<img height="70%" width="70%" alt="Screenshot 2024-02-12 at 1 59 44 PM" src="https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/08986155-8f45-4c8b-8fa6-9bbf8e1fa480">




- After installation, open wireshark click on the capture button, and observe the network traffic.


<img height="70%" width="70%" alt="wireshark capture button" src="https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/d862761c-f77f-4e18-a84a-b665efb5bb41">



<img height="70%" width="70%" alt="Screenshot 2024-02-12 at 2 54 56 PM" src="https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/2c022360-f13b-40bd-a777-6e1e5ad11da6">


- Filter for ICMP(Internet Control Message Protocol) traffic.
- ICMP determines whether or not data is reaching its intended destination. 
- Open up Windows PowerShell and ping VM-2 private IP address.
- You can find VM-2 private IP address in the Azure Portal under networking.


<img height="70%" width="70%" alt="ping icmp" src="https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/1f1330ff-45d8-48f9-9ec7-3a98b81c4b7d">


- You can observe the ping request in WireShark.
- Source: 10.0.0.4 (VM-1 private IP address).
- Destination: 10.0.0.5 (VM-2).
- Protocol: ICMP
- Request followed by the reply from VM-2.


<img height="70%" width="70%" alt="Screenshot 2024-02-12 at 3 02 25 PM" src="https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/21d5a439-4b42-4608-8cbf-492b7dadd454">



- You can also observe the traffic from a website.
- From The Windows 10 VM, open the command line or PowerShell and attempt to ping a public website (such as www.google.com) and observe the traffic in WireShark
- The destination IP address (172.217.12.142) is Google's public IP address.

<img height="70%" width="70%" alt="Screenshot 2024-02-12 at 3 10 29 PM" src="https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/6fd6baf0-35f1-4959-9836-7cee54703874">


<img height="70%" width="70%" alt="Screenshot 2024-02-12 at 3 10 48 PM" src="https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/57566dd1-c168-43b1-a3d6-e66ce14fbb83">


- Initiate a perpetual/non-stop ping from your Windows 10 VM to your Ubuntu VM.
- The command for perpetual ping is -t (ping 10.0.0.5 -t).


<img height="70%" width="70%" alt="non stop ping" src="https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/375dda64-5621-4edc-b144-036ea109688d">



<img height="70%" width="70%" alt="Screenshot 2024-02-12 at 3 19 20 PM" src="https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/f5e663b0-c83a-434f-8061-94dca41ca1ea">



- To get a basic idea of how firewalls work we will block IMCP traffic from VM-2 firewall and observe the results.
- Go back to the Azure portal go to Network Security groups and click on VM-2.


<img height="70%" width="70%" alt="network securty group" src="https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/5dd1d921-dcc6-49c3-9460-f2c4ce6ed555">



<img height="70%" width="70%" alt="Screenshot 2024-02-12 at 3 23 16 PM" src="https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/1c247ca5-763c-4032-8c9b-7c8601c5ca8e">


- From there click on Inbound security rules and click Add.


<img height="70%" width="70%" alt="Screenshot 2024-02-12 at 3 25 00 PM" src="https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/ec2c8be3-78ee-44e9-b720-e0c9324171b5">



<img height="70%" width="70%" alt="Screenshot 2024-02-12 at 3 26 40 PM" src="https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/7bd2421f-c4d3-42af-a69b-901b6d2b5d5c">


- Add inbound security rule.
- Protocol: ICMP
- Action: Deny
- Priority: 200(We want this on the top of the list of Inbound Security Rules)

<img height="70%" width="70%" alt="Screenshot 2024-02-12 at 3 29 09 PM" src="https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/0be099c7-f77e-4bdd-9953-df9d6977dd26">


<img height="70%" width="70%" alt="Screenshot 2024-02-12 at 3 33 37 PM" src="https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/0414da4d-007b-4233-b681-4acef6dabaf8">


- Back in the Windows 10 VM, observe the ICMP traffic in WireShark and the command line Ping activity
- Re-enable ICMP traffic for the Network Security Group your Ubuntu VM is using
- Back in the Windows 10 VM, observe the ICMP traffic in WireShark and the command line Ping activity (should start working)


<img height="70%" width="70%" alt="Screenshot 2024-02-12 at 3 34 32 PM" src="https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/540ff695-baae-468e-9fa5-fef24a69f3c1">



<h3>Observe SSH Traffic</h3>
