<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used</h2>

- Windows 10 (21H2)

<h2>List of Prerequisites</h2>

- Create a Resource Group in Microsoft Azure
- Create a Windows 10 Virtual Machine (VM) with 2-4 Virtual Cups
- Allow the VM to create a new Virtual Network (Vnet)
- Name the Virtual Machine Vm-osticket with Username: 'jasonregj' and a password
- Login to Microsoft Remote Desktop with your VM public IP Address
- Download IIS with CGI (use standard configurations for all Launch Config wizards)
- Download/install PHP Manager for IIS (V1.5.0.msi)
- Download/install Rewrite Module (rewrite_amd64_en-US.msi)
- Create the directory C:\PHP
- Download PHP 7.3.8 (nts-Win32-VC15-x86.zip)/unzip contents into C:\PHP
- Download/install VC_redist.x86.exe
- Download/install MySQL 5.5.62 (mysql-5.5.62-win32.msi)

<h2>Installation Steps</h2>

<p>
Create your Resource Group in Microsoft Azure (must have a subscription). 
</p>
<p>
<img src="https://i.imgur.com/m2m7ppf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create an Azure Virtual Machine Windows 10, 4 vCPUs
</p>
<p>
- Name the VM 'VM-osTicket'
</p>
<p>
- Username: 'jasonregj' amd choose a password
</p>

<p>
<img src="https://i.imgur.com/EUL1Qbz.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/IqIVw9f.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
Once you click the create button for your VM, you can view all the resources within the VM under the Resource Group "VMs_Lab02."
</p>
<p>
<img src="https://i.imgur.com/4hzXbO9.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
Download Microsoft Remote Desktop from Google. Open the application and copy the public IP address from your VM's Virtual Network and copy it into the Remote Desktop "Add PC" PC Name. You can view this information from Home -> VM-osTicket. Login with username 'jasonregj' and the password created.
</p>
<p>
<img src="https://i.imgur.com/2oKJfXj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/lmeECL3.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/fyFZWsy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Select 'Continue'
</p>
<p>
<img src="https://i.imgur.com/kIuM5jG.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/rXsvrRE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
What we have now done is created a Virtual desktop computer with a Virtual network (separate from our actual computer), a network security group (NSG or firewall), a network interface card (NIC or virtual ethernet port), a public IP address, and a storage disk. For the osTicket demonstrations, we can now login as an administrator in one computer/network and a user in the other virtual computer/network (or vice versa), test connectivity between the networks, and confirm configurations of roles, departments, agents, teams, users, SLAs, and ensure help topics are in place via an admin and a user. 
  
<p>
Download and install necessary files for successful osTicket installation
</p>
<p>
<img src="https://i.imgur.com/BvYAXlT.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Open IIS as an Admin.
</p>
<p>
<img src="https://i.imgur.com/PBzT3D5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Register PHP from within IIS. Reload IIS (open IIS, stop and start the server).
</p>
<br />


<p>
From here we are going to install osTicket v1.15.8.
</p>
<br />

<p>
<img src="https://i.imgur.com/xuQgiS1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Download osTicket from the Installation Files Folder provided then extract and copy "upload" folder to c:\inetpub\wwwroot. Within c:\inetpub\wwwroot, Rename "upload" to "osTicket"
</p>

<p>
Reload IIS (open IIS, Stop and start the server). Go to sites -> Default -> osTicket and on the right click "Browse *:80." Note that some extensions are not enabled so go back to IIS, sites -> Default -> osTicket, double-click PHP Manager and click "Enable or disable an extension."
</p>
<p>
<img src="https://i.imgur.com/nyfHhS9.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
-Enable: php_imap.dll
</p>
<p>
-Enable: php_intl.dll
</p>
<p>
-Enable: php_opcache.dll
</p>
<p>
Refresh the osTicket site in your browser and observe the changes (see image below)
</p>
<p>
<img src="https://i.imgur.com/0fCHI26.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/RTJtnX3.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
Rename ost-config.php from "C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php" to "C:\inetpub\wwwroot\osTicket\include\ost-config.php"
</p>
<p>
Assign Permissions: ost-config.php
</p>
<p>
-Disable inheritance -> Remove All
</p>
<p>
-New Permissions -> Everyone -> All
</p>

<p>
<img src="https://i.imgur.com/PBwSxFU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Continue Setting up osTicket in the browser (click Continue).
</p>
<p>
-Name Helpdesk
</p>
<p>
-Default email (receives email from customers)
</p>

<p>
From the provided installation files, download/install HeidiSQL
</p>
<p>
-Open Heidi SQL
</p>
<p>
-Create a new session, user/password (established when installing MySQL)
</p>
<p>
-Connect to the session
</p>
<p>
-Create a database called "osTicket" (see image below)
</p>
<img src="https://i.imgur.com/znZ0TYL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

</p>
<img src="https://i.imgur.com/aC8pUeH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Continue Setting up osTicket in the browser.
</p>
<p>
-MySQL Database: osTicket
</p>
<p>
-MySQL Username: (set up earlier from MySQL install)
</p>
<p>
-MySQL Password: (set up earlier from MySQL install)
</p>
<p>
Click "Install Now!" The following images below show the osTicket application in browser as well as the admin login prompt and logged in account home page. 
</p>

</p>
<img src="https://i.imgur.com/EB3Q7gR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
</p>
<img src="https://i.imgur.com/90jhZAr.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
</p>
<img src="https://i.imgur.com/IuNhxVS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
We will display the instructions for creating and using Virtual Machines and Remote Desktop in the osTicket Post-Installation Repository
</p>
<br />
