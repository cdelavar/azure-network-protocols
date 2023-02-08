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
<img src="https://imgur.com/q7JK80w.png" height="80%" width="80%" alt="Network Watcher Topology"/>
</p>
<p>
Network Watcher - Topology
</p>
<br />

<p>
<img src="https://imgur.com/QnCStZb.png" height="80%" width="80%" alt="Download Wireshark"/>
</p>
<p>
Download Wireshark from wireshark.org and install everything by the defaults.
</p>
<br />

<p>
<img src="https://imgur.com/87hBh49.png" height="80%" width="80%" alt="Capture Packets"/>
</p>
<p>
Press the shark fin icon in the upper left corner to start capturing packets.
</p>
<br />

<p>
<img src="https://imgur.com/kwBRKVo.png" height="80%" width="80%" alt="Filter ICMP"/>
</p>
<p>
Type ICMP into the input box at the top and notice there are no packets being sent or received.
</p>
<br />

<p>
<img src="https://imgur.com/Itdf5fP.png" height="80%" width="80%" alt="Create Linux VM"/>
</p>
<p>
Find the private IP of the Ubuntu virtual machine and ping it using Powershell. Notice the packets sent and received.
</p>
<br />

<p>
<img src="https://imgur.com/EuSUWPd.png" height="80%" width="80%" alt="Wireshark ICMP Packets"/>
</p>
<p>
You can see the pings and replies in Wireshark.
</p>
<br />

<p>
<img src="https://imgur.com/emkGQ1l.png" height="80%" width="80%" alt="Ping G"/>
</p>
<p>
Ping google.com in Powershell (ping google.com -4) and note the traffic in Wireshark.
</p>
<br />

<p>
<img src="https://imgur.com/ic6RmUx.png" height="80%" width="80%" alt="Sent Data"/>
</p>
<p>
You can see the data that's being sent on the bottom of the Wireshark analyzer, in this case, junk data including letters of the alphabet.
</p>
<br />

<p>
<img src="https://imgur.com/mxIwDJs.png" height="80%" width="80%" alt="Perpetual Ping"/>
</p>
<p>
Initiate a perpetual ping from VM-1 to VM-2 in Powershell (ping 10.0.0.5 -t). While this is pinging, we're going to change the firewall on the Linux virtual machine to not allow ICMP traffic to come through. 
</p>
<br />

<p>
<img src="https://imgur.com/qYShmmm.png" height="80%" width="80%" alt="Azure NSG"/>
</p>
<p>
We'll change the firewall settings through the Azure portal so go to portal.azure.com and type Network Security Group in the search bar.
</p>
<br />

<p>
<img src="https://imgur.com/gqkKzqe.png" height="80%" width="80%" alt="Inbound Security Rules"/>
</p>
<p>
Click on the Linux NSG, then Inbound security rules on the left side panel. The firewall rules currently in effect for will be displayed.
</p>
<br />

<p>
<img src="https://imgur.com/nh15xWy.png" height="80%" width="80%" alt="Block ICMP Traffic"/>
</p>
<p>
We want to deny inbound ICMP traffic so it blocks the pings coming from the Windows VM. Click on +Add to add an inbound security rule. The Source, Source port ranges, and Destination will be Any(*), Click on ICMP under Protocol, this will change the Destination port ranges to Any(*). Under Action, click Deny. Any ICMP traffic coming from any source port to any destination port will be denied. 
</p>
<br />

<p>
<img src="https://imgur.com/nXpesvd.png" height="80%" width="80%" alt="Rule Priority"/>
</p>
<p>
Set the Priority to 200 so the rule takes effect before the others. Name the rule DENY_ICMP_PING_FROM_ANYWHERE. Click Add.
</p>
<br />

<p>
<img src=".png" height="80%" width="80%" alt="Create Linux VM"/>
</p>
<p>
Lorem ipsum
</p>
<br />
