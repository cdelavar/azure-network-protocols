<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />


<h2>Video Demonstration</h2>

- ### [YouTube: Azure Virtual Machines, Wireshark, and Network Security Groups](https://www.youtube.com)

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

- Step 1
- Step 2
- Step 3
- Step 4

<h2>Actions and Observations</h2>

<p>
<img src="https://imgur.com/B59g8fY.png" height="80%" width="80%" alt="Create Resources"/>
</p>
<p>
Create resources in Azure - two virtual machines, one running Windows and the other Ubuntu. When you create the virtual machine, Azure will create the virtual network and subnet automatically. Go to portal.azure.com and type in Virtual Machines in the search bar. Click Create - Azure virtual machine. 
</p>
<br />

<p>
<img src="https://imgur.com/MmGr4eY.png" height="80%" width="80%" alt="Create Windows VM"/>
</p>
<p>
Under the Resource group box, click Create new and give your new resource a name. In this case, it's NSG. For the base operating system image, choose Windows 10, and choose a VM size, preferably with 2 vcpus. Click Review + create.
</p>
<br />

<p>
<img src="https://imgur.com/SkugI5e.png" height="80%" width="80%" alt="Create Linux VM"/>
</p>
<p>
Create the second virtual machine with an Ubuntu image. Make sure to use the same resource group as the first VM, as this will place it in the same virtual network. Also make sure to use the same Region as the first VM.
</p>
<br />

<p>
<img src=".png" height="80%" width="80%" alt="Create Linux VM"/>
</p>
<p>
Lorem ipsum
</p>
<br />

<p>
<img src=".png" height="80%" width="80%" alt="Create Linux VM"/>
</p>
<p>
Lorem ipsum
</p>
<br />

<p>
<img src=".png" height="80%" width="80%" alt="Create Linux VM"/>
</p>
<p>
Lorem ipsum
</p>
<br />

<p>
<img src=".png" height="80%" width="80%" alt="Create Linux VM"/>
</p>
<p>
Lorem ipsum
</p>
<br />
