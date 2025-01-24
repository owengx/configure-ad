<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Creation of two virtual machines. One will run the Windows server and the other Windows 10
- Create a domain on the Windows server machine which will be our domain controller (DC-1) and then join the Windows 10 (client-1) computer to the domain
- Create users and log in utilizing one of the created users. Simulating real-life active directory environment

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://i.imgur.com/oasEim6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Both the domain controller (DC-1) and the client (Client-1) computer will have a virtual NIC and IP address. For the client to join the domain will first need to tell client-1 to utilize the DNS server of the domain controller. We'll set the DNS IP address of client-1 to the same IP address as the domain controller.
</p>
<br />

<p>
<img src="https://i.imgur.com/VSpRR9W.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create a Resource Group, Create a Virtual Network and Subnet, and Create the Domain Controller VM (Windows Server 2022) named “DC-1”. We will do the same when creating the client-1 vm.

</p>
<br />

<p>
<img src="https://i.imgur.com/AL5Hi0V.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After the VM is created, we'll set the Domain Controller’s NIC Private IP address to be static. We'll then pull the public IP address from DC-1 by navigating back to virtual machines in Azure and looking for its corresponding IP address. Once we've got the public IP we can go ahead and remote desktop into that PC by utilizing the chosen credentials we created while setting up the DC-1 VM. 
</p>
<br />
