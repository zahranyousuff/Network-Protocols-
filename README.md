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


- Filter for ICMP traffic.
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

![image](https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/fb0089ca-7a18-48b5-9d59-8cdd72902bce)


![image](https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/73aa38e8-8a56-408c-bffd-e36c49a50661)


- Initiate a perpetual/non-stop ping from your Windows 10 VM to your Ubuntu VM.
- The command for perpetual ping is -t.


![image](https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/eb64440a-fe83-4c0f-a277-dc6554aaaa47)


![image](https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/c8e7f881-a9e1-499d-a33a-fb5de79d73f4)


- To get a basic idea of how firewalls work we will block IMCP traffic from VM-2 firewall and observe the results.
- Go back to the Azure portal go to Network Security groups and click on VM-2.


![image](https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/26c5ce58-42f3-4ab1-a121-50cdf11b0c02)


![image](https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/35f54d96-706e-45d9-b65c-5baeb150f21f)


- From there click on Inbound security rules and click Add.


![image](https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/c8fc5055-ec7f-44bb-8530-9926ab0ad421)


<img width="800" alt="Screenshot 2024-02-12 at 3 26 40 PM" src="https://github.com/zahranyousuff/Network-Protocols-/assets/159392784/dd166cc7-abf4-4f5d-8590-fc8cc698ec12">


