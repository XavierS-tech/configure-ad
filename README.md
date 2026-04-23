# configure-ad
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

- Windows Server 2025
- Windows 11 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Install Active Directory

- Create a Domain Admin user within the domain

- Join Client-1 to your domain (mydomain.com)

- Setup Remote Desktop for non-administrative users on Client-1
- Create a bunch of additional users and attempt to log into client-1 with one of the users



<h2>Deployment and Configuration Steps</h2>

<p>
<img width="1100" height="632" alt="image" src="https://github.com/user-attachments/assets/6a40230f-7496-4356-90b3-6541cebdba14" />

</p>
<p>
Install Active Directory
—
Login to DC-1 and install Active Directory Domain Services
Promote as a DC: Setup a new forest as mydomain.com (can be anything, just remember what it is)
Restart and then log back into DC-1 as user: mydomain.com\labuser


</p>
<br />

<p>
<<img width="1232" height="815" alt="image" src="https://github.com/user-attachments/assets/c0007202-cbb2-48ac-94af-98f41289bb78" />

<p>
Create a Domain Admin user within the domain
—
In Active Directory Users and Computers (ADUC), create an Organizational Unit (OU) called “_EMPLOYEES”
Create a new OU named “_ADMINS”
Create a new employee named “Jane Doe” (same password) with the username of “jane_admin” / Cyberlab123!
Add jane_admin to the “Domain Admins” Security Group
Log out / close the connection to DC-1 and log back in as “mydomain.com\jane_admin”
User jane_admin as your admin account from now on

</p>
<br />

<p>
<<img width="1120" height="757" alt="image" src="https://github.com/user-attachments/assets/6e4102f1-760e-469b-b850-e277da7e2011" />

</p>
<p>
Setup Remote Desktop for non-administrative users on Client-1
—
Log into Client-1 as mydomain.com\jane_admin
Open system properties
Click “Remote Desktop”
Allow “domain users” access to remote desktop
You can now log into Client-1 as a normal, non-administrative user now
Normally you’d want to do this with Group Policy that allows you to change MANY systems at once

</p>
<br />
