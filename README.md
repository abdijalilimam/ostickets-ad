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
Create two Virtual Machines, name them appropriately, and make sure they have VNET when creating.</p>
<p>
<img width="1321" alt="image" src="https://github.com/abdijalilimam/ostickets-ad/assets/137457871/f92bc579-29d5-4e8c-ab2e-aace17e0f8c8">
</p>

<br /> 

<p>
Configure the IP setting on the Domain Controller machine and set the Domain Controller NIC private IP address from Dynamic to Static. 
</p>

<p>
<img width="1434" alt="Screenshot 2023-08-27 at 11 49 15 AM" src="https://github.com/abdijalilimam/ostickets-ad/assets/137457871/2776344e-d1a4-41c3-ba8c-d12a07c7370d">
</p>

<br />
<p>
Login to Client-1 with Remote Desktop and try to ping the Domain controller private IP address with ping -t 10.0.0.4 (perpetual ping) your IP might be slightly different.
</p>

<p>
<img width="1440" alt="Screenshot 2023-08-27 at 12 03 48 PM" src="https://github.com/abdijalilimam/ostickets-ad/assets/137457871/bbd58209-5777-4525-be35-329d66298da8">
</p>

<p>
Login to the Domain Controller and enable ICMPv4 on the local Windows firewall
Check back at Client-1 to see the ping succeed
</p>
<p>
  <img width="1435" alt="Screenshot 2023-08-27 at 12 08 01 PM" src="https://github.com/abdijalilimam/ostickets-ad/assets/137457871/5a6f20b8-0a74-4a54-9af8-e62150844519">
</p>
<p>
  <img width="1438" alt="Screenshot 2023-08-27 at 12 08 28 PM" src="https://github.com/abdijalilimam/ostickets-ad/assets/137457871/fb5f0507-2754-41f8-83f2-2b5b10828bcd">
</p>

<p>
  Now let's download AD(Active Directory) on our DC-1 machine You can start this by logging into your DC-1 machine and download Active Directory. setup new forest as "mydomain.com" or it can be anything you want as long as you remember what it is restart the VM and log back in. Firstly if you want to know if you are on the right VM you can start by opening "cmd" and typing in "hostname"
</p>
<p>
  <img width="1440" alt="Screenshot 2023-08-12 at 8 00 46 PM" src="https://github.com/abdijalilimam/ostickets-ad/assets/137457871/9678391e-d2c7-4275-b7b9-7d6ce7d3cf50">
</p>

<p>
  My new forest is "abdijalil.com" yours can be anything you want as long as you remember.
</p>
<p>
  <img width="1440" alt="Screenshot 2023-08-27 at 12 18 10 PM" src="https://github.com/abdijalilimam/ostickets-ad/assets/137457871/664d851f-b8ec-4d74-8630-ee2a3adc0386">
</p>

<p>
  We can start now creating Organizational Units (OU) after we complete our previous step. Let's first create an Organizational Unit named _EMPLOYEES. In order to do that right-click on the domain area. Select new--> Organizational Unit and fill out the sections. Then click inside of your OU and right-click it, select new and select user, and fill out the information for your new user. The user should be named Jane Doe, she is going to be an Admin so her username will be Jane_admin. Lastly, add Jane to the domain admin's security group. Create another OU named _ADMINS
</p>
<p>
  ![Uploading Screenshot 2023-08-27 at 12.37.49 PM.png…]()
</p>
<p>
  ![Uploading Screenshot 2023-08-27 at 12.42.21 PM.png…]()
</p>

<br />
