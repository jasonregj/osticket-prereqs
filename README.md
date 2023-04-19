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

- Download IIS with CGI (use standard configurations for all Launch Config wizards)
- Download/install PHP Manager for IIS (V1.5.0.msi)
- Download/install Rewrite Module (rewrite_amd64_en-US.msi)
- Create the directory C:\PHP
- Download PHP 7.3.8 (nts-Win32-VC15-x86.zip)/unzip contents into C:\PHP
- Download/install VC_redist.x86.exe
- Download/install MySQL 5.5.62 (mysql-5.5.62-win32.msi)

<h2>Installation Steps</h2>

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
