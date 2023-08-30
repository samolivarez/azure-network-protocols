<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Computer)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Remote into VMs
- Use traffic filter program
- Inspect traffic protocols
- Edit/set traffic rules

<h2>Actions and Observations</h2>

<p>
<img src="https://i.imgur.com/fvbiozs.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
This tutorial begins with the prerequesite of having created 2 Virtual Machines; in our case as the above image shows we have VM1 and VM2 in which we will remote into in order to observe the traffic exchanges and protocols between the two VMs using a traffic analyzer tool called Wireshark.
</p>
<br />

<p>
<img src="https://i.imgur.com/9os3jxk.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next, from Windows Powershell command line in VM1 and using the ICMP traffic protocol we are "pinging" from VM1 to VM2 and observe the IP traffic "reply" from VM2 in the command line.
</p>
<br />

<p>
<img src="https://i.imgur.com/LGP0GGR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next, from our Wireshark taffic analyzer tool we observe the IP address traffic exchange between VM1 and VM2.
</p>
<br /># azure-network-protocols

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br /># azure-network-protocols
