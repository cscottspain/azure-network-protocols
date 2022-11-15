<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />


<h2>Video Demonstration</h2>

- ### (COMING SOON!)[YouTube: Azure Virtual Machines, Wireshark, and Network Security Groups](https://www.youtube.com)

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

- Create Resources
- Observe ICMP Traffic
- Observe SSH Traffic
- Observe DHCP Traffic
- Observe DNS Traffic
- Observe RDP Traffic

<h2>Actions and Observations</h2>

<p><strong>Part 1 (Create our Resources)</strong></p>
<ul>
<li><strong><strong>Create a Resource Group</strong></strong></li>
</ul>
<ul>
<li><strong>Create a Windows 10 Virtual Machine (VM)</strong></li>
</ul>
<ul>
<li><strong>While creating the VM, select the previously created Resource Group</strong></li>
</ul>
<ul>
<li><strong>While creating the VM, allow it to create a new Virtual Network (Vnet) and Subnet</strong></li>
</ul>
<ul>
<li><strong>Create a Linux (Ubuntu) VM</strong></li>
</ul>
<ul>
<li><strong>While create the VM, select the previously created Resource Group and Vnet</strong></li>
</ul>
<ul>
<li><strong>Observe Your Virtual Network within Network Watcher</strong></li>
</ul>
<p><strong>Part 2 (Observe ICMP Traffic)</strong></p>
<ul>
<li><strong><strong>Use Remote Desktop to connect to your Windows 10 Virtual Machine</strong></strong></li>
</ul>
<ul>
<li><strong>Within your Windows 10 Virtual Machine, Install Wireshark</strong></li>
</ul>
<ul>
<li><strong>Open Wireshark and filter for ICMP traffic only</strong></li>
</ul>
<ul>
<li><strong>Retrieve the private IP address of the Ubuntu VM and attempt to ping it from within the Windows 10 VM</strong></li>
</ul>
<ul>
<li><strong>Observe ping requests and replies within WireShark</strong></li>
</ul>
<ul>
<li><strong>From The Windows 10 VM, open command line or PowerShell and attempt to ping a public website (such as </strong><a href="http://www.google.com"><strong>www.google.com</strong></a><strong>) and observe the traffic in WireShark</strong></li>
</ul>
<ul>
<li><strong>Initiate a perpetual/non-stop ping from your Windows 10 VM to your Ubuntu VM</strong></li>
</ul>
<ul>
<li><strong>Open the Network Security Group your Ubuntu VM is using and disable incoming (inbound) ICMP traffic</strong></li>
</ul>
<ul>
<li><strong>Back in the Windows 10 VM, observe the ICMP traffic in WireShark and the command line Ping activity</strong></li>
</ul>
<ul>
<li><strong>Re-enable ICMP traffic for the Network Security Group your Ubuntu VM is using</strong></li>
</ul>
<ul>
<li><strong>Back in the Windows 10 VM, observe the ICMP traffic in WireShark and the command line Ping activity (should start working)</strong></li>
</ul>
<ul>
<li><strong>Stop the ping activity</strong></li>
</ul>
<p><strong>Part 2 (Observe SSH Traffic)</strong></p>
<ul>
<li><strong><strong>Back in Wireshark, filter for SSH traffic only</strong></strong></li>
</ul>
<ul>
<li><strong>From your Windows 10 VM, &ldquo;SSH into&rdquo; your Ubuntu Virtual Machine (via its private IP address)</strong></li>
</ul>
<ul>
<li><strong>Type commands (ls, pwd, etc) into the linux SSH connection and observe SSH traffic spam in WireShark</strong></li>
</ul>
<ul>
<li><strong>Exit the SSH connection by typing &lsquo;exit&rsquo; and pressing [Enter]</strong></li>
</ul>
<p><strong>Part 2 (Observe DHCP Traffic)</strong></p>
<ul>
<li><strong><strong>Back in Wireshark, filter for DHCP traffic only</strong></strong></li>
</ul>
<ul>
<li><strong>From your Windows 10 VM, attempt to issue your VM a new IP address from the command line (ipconfig /renew)</strong></li>
</ul>
<ul>
<li><strong>Observe the DHCP traffic appearing in WireShark</strong></li>
</ul>
<p><strong>Part 2 (Observe DNS Traffic)</strong></p>
<ul>
<li><strong><strong>Back in Wireshark, filter for DNS traffic only</strong></strong></li>
</ul>
<ul>
<li><strong>From your Windows 10 VM within a command line, use nslookup to see what google.com and disney.com&rsquo;s IP addresses are</strong></li>
</ul>
<ul>
<li><strong>Observe the DNS traffic being show in WireShark</strong></li>
</ul>
<p><strong>Part 2 (Observe RDP Traffic)</strong></p>
<ul>
<li><strong><strong>Back in Wireshark, filter for RDP traffic only (tcp.port == 3389)</strong></strong></li>
</ul>
<ul>
<li><strong>Oserve the immediate non-stop spam of traffic? Why do you think it&rsquo;s non-stop spamming vs only showing traffic when you do an activity?</strong></li>
</ul>
<ul>
<li><strong>Answer: because the RDP (protocol) is constantly showing you a live stream from one computer to another, therefor traffic is always being transmitted</strong></li>
</ul>
