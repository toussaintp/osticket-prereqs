<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Microsoft Azure account
- Azure Windows 11 Virtual Machine
- Remote Desktop Connection (RDP)
- Internet Information Services (IIS) enabled
- osTicket Installation Files
- PHP Manager for IIS
- URL Rewrite Module
- Microsoft Visual C++ Redistributable
- MySQL Server
- HeidiSQL Database Management Tool

<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 1: Create an Azure Virtual Machine
Create a Windows 11 Virtual Machine in Microsoft Azure.

- Resource Group: osTicket
- Virtual Machine Name: osticket-vm
- Operating System: Windows 11 Pro
- Size: Standard B2s
- Username and Password created during deployment

After deployment, connect to the VM using Remote Desktop Protocol (RDP).
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 2: Install IIS
Open Control Panel → Programs → Turn Windows Features On or Off.

Enable:

- Internet Information Services (IIS)
- World Wide Web Services
- Application Development Features
  - CGI

Click OK and allow Windows to install the required features.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 3: Download osTicket Installation Package
Download the osTicket installation package and supporting files.

These files include:

- PHP Manager for IIS
- URL Rewrite Module
- Visual C++ Redistributable
- MySQL Server
- HeidiSQL
- osTicket
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 4: Install PHP Manager and URL Rewrite
Install:

1. PHP Manager for IIS
2. URL Rewrite Module

These components allow IIS to properly run PHP applications such as osTicket.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 5: Install Visual C++ Redistributable
Install the Microsoft Visual C++ Redistributable package.

This provides required runtime libraries for PHP and other dependencies.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 6: Install PHP
Extract PHP to:

C:\PHP

Open IIS Manager.

Using PHP Manager:

- Register PHP
- Verify PHP is recognized by IIS
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 7: Install MySQL
Install MySQL Server.

During installation:

- Create a root password
- Select Typical Setup

Verify MySQL service is running after installation.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 8: Install HeidiSQL
Install HeidiSQL.

Connect to MySQL using:

- Server: localhost
- Username: root
- Password: (your password)

Verify successful database connection.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 9: Install osTicket
Extract osTicket files.

Copy the upload folder contents to:

C:\inetpub\wwwroot\osTicket

Rename:

upload → osTicket

Restart IIS.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 10: Configure IIS for osTicket
Open IIS Manager.

Navigate to:

Sites → Default Web Site → osTicket

Enable:

- PHP Manager
- Required PHP Extensions

Refresh the website and verify osTicket setup page loads.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 11: Configure osTicket File Permissions
Rename:

ost-sampleconfig.php

to

ost-config.php

Modify Security Permissions:

- Disable inheritance
- Remove unnecessary users
- Grant Full Control to Everyone temporarily
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 12: Create osTicket Database
Open HeidiSQL.

Create a new database named:

osTicket

This database will store tickets, users, departments, and configuration settings.
</p>
<br />


<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 13: Complete Web Installation
Browse to:

http://localhost/osTicket

Enter:

- Helpdesk Name
- Default Email
- Admin Username
- Admin Password

Database Settings:

- MySQL Database: osTicket
- Username: root
- Password: your password

Click Install Now.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

