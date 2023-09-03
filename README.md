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

- Create two VMs (client 1) and (Domain Controller ) with the same VNET on Azure.
- Change the IP configuration of the DC machine from Dynamic to Static.
- Join the client machine to the domain.
- Configure the DNS setting on the client machine.
- Client machine uses DC as DNS server.
  
<p>
<img width="587" alt="image" src="https://github.com/abdijalilimam/ostickets-ad/assets/137457871/aa0f0d30-07fc-443e-b210-b8cc47af2b0d">
</p>

<p>
Create two Virtual Machines, name them appropriately and make sure they have VNET when creating.</p>
<p>
<img width="1321" alt="image" src="https://github.com/abdijalilimam/ostickets-ad/assets/137457871/f92bc579-29d5-4e8c-ab2e-aace17e0f8c8">
</p>

<br /> 

<p>
Configure the IP setting on the Domain Controller machine from Dynamic to Static. 
</p>

<p>
<img width="1434" alt="Screenshot 2023-08-27 at 11 49 15 AM" src="https://github.com/abdijalilimam/ostickets-ad/assets/137457871/2776344e-d1a4-41c3-ba8c-d12a07c7370d">
</p>

<br />
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<br />
