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
- Use Wireshark Traffic analyzer tool
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
Next, from Windows Powershell command line in VM1 and using the ICMP traffic protocol we are "pinging" from VM1 to VM2 and observe the IP traffic "reply" from VM2 in the command line. This is done by typing from Vm1's command line the "ping command along with VM2's private IP address.
</p>
<br />

<p>
<img src="https://i.imgur.com/LGP0GGR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next, from our Wireshark taffic analyzer tool we observe the "ping" command line IP address traffic exchange between VM1 and VM2.
</p>
<br /># azure-network-protocols

<p>
<img src="https://i.imgur.com/zNJpsqZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next, we begin to edit the "inbound traffic rules" for VM2. The above image shows we are denying ICMP traffic for VM2 from Azure Network Security Rules.
</p>
<br /># azure-network-protocols

<p>
<img src="https://i.imgur.com/pTr5DZL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next, after denying ICMP traffic for VM2 in Azure we see in the Wireshark analyzer tool that ICMP traffic in which the "ping" command uses is blocked. You only see the "request" but no response.
</p>
<br /># azure-network-protocols

<p>
<img src="https://i.imgur.com/UGNxjaa.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next, in order for VM2 to once again receive ICMP traffic we need to edit the Azure Network Security Rules for VM2 to "allow" ICMP traffic as the above image shows. 
</p>
<br /># azure-network-protocols

<p>
<img src="https://i.imgur.com/GbrvjbE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next, as the above image shows; VM2 with IP address of 10.0.0.5 is once again allowing ICMP traffic to be received from VM1's IP address (10.0.0.4) which can be confirmed by observing the request/reply interaction between the two IP addresses in the Wireshark traffic analyzer tool.
</p>
<br /># azure-network-protocols

<p>
<img src="https://i.imgur.com/yX5TylX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next, we start to observe SSH protocol traffic between VM1 and VM2 in Wireshark. As the above image shows this can be done by first typing SSH in the Wireshark traffic bar insted of ICMP. Secondly to start observing SSH traffic flow between the two VMs we need to open a powershell command line in VM1 then type SSH along with VM2's username at Vm2's private IP address. For example:
SSH VM2username@VM2privateIPaddress 
</p>
<br /># azure-network-protocols

<p>
<img src="https://i.imgur.com/X1q1k9x.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next, we are start to observe DNS protocol traffic between Vm1 and VM2 in Wireshark.  This is done by first exiting from our previous SSH protocol traffic connection between VM1 and VM2 by typing "exit" in the command line of VM2 to close out the sessio. Now we can type DNS in the wireshark traffic filter bar instead of SSH then proceed to VM1s command line and type for example "nslookup www.google.com" and will start to see the traffic exchange in wireshark between Vm1 and the IP address of www.google.com
</p>
<br /># azure-network-protocols

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br /># azure-network-protocols
