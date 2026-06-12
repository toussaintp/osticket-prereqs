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


Step 1: Create an Azure Virtual Machine
  
Create a Windows 10 Virtual Machine in Microsoft Azure.

- Resource Group: osTicket
- Virtual Machine Name: osticket-vm
- Operating System: Windows 10 Pro
- Size: Standard D2s v3 2vcpus
- Username and Password created during deployment

<p>
<img width="871" height="894" alt="Create a Windows 10 Virtual Machine in Microsoft Azure" src="https://github.com/user-attachments/assets/b8280aff-2202-4203-b437-f56972b9aa36" />
</p>
<p>

After deployment, connect to the VM using Remote Desktop Protocol (RDP).

<p>
<img width="931" height="756" alt="RDP to virtual machine" src="https://github.com/user-attachments/assets/d3bfa779-47a7-427a-a90a-7dddcf3d0bd8" />
</p>
<p>

</p>
<br />


Step 2: Install IIS

Open Control Panel → Programs → Turn Windows Features On or Off.

Enable:

- Internet Information Services (IIS)
- World Wide Web Services
- Application Development Features
  - CGI

Click OK and allow Windows to install the required features.

<p>
<img width="621" height="713" alt="Install IIS" src="https://github.com/user-attachments/assets/b8588838-bcf4-41ef-ba04-f21a0d30d988" />
</p>
<p>
</p>
<br />


Step 3: Download osTicket Installation Package

Download the osTicket installation package and supporting files.
https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD

These files include:

- PHP Manager for IIS
- URL Rewrite Module
- Visual C++ Redistributable
- MySQL Server
- HeidiSQL
- osTicket
- PHP binaries
  
  <p>
<img width="657" height="570" alt="download osTicket installation file" src="https://github.com/user-attachments/assets/f8b4d76a-43f8-4300-9323-acfbdd67d36f" />
</p>
<p>
  
</p>
<br />


Step 4: Install PHP Manager and URL Rewrite
Install:

1. PHP Manager for IIS
<p>
<img width="861" height="682" alt="php manager installed" src="https://github.com/user-attachments/assets/a31e1773-ea2a-4368-88e1-24ffdecf74c4" />
</p>
<p>

2. URL Rewrite Module
<p>
<img width="885" height="700" alt="rewrite installed" src="https://github.com/user-attachments/assets/f54f6307-2c94-4a61-9165-835caff97953" />
</p>
<p>

These components allow IIS to properly run PHP applications such as osTicket.
</p>
<br />

Step 5 - Extract php binaries

Create the directory C:\PHP

Go to file explorer -> c: drive -> create folder PHP 

From the “osTicket-Installation-Files” folder, unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder

<p>
<img width="878" height="669" alt="extract php binaries" src="https://github.com/user-attachments/assets/d751ec31-0e35-4418-86fc-2323a6ff87e6" />
</p>
<p>
</p>
<br />


Step 6: From the “osTicket-Installation-Files” folder, install VC_redist.x86.exe.
  
Install the Microsoft Visual C++ Redistributable package.

<p>
<img width="872" height="663" alt="visual c installed" src="https://github.com/user-attachments/assets/b588daf9-dc51-4070-a1e5-07a94711cd5e" />
</p>
<p>

This provides required runtime libraries for PHP and other dependencies.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 7: Install PHP
Extract PHP to:

C:\PHP

Open IIS Manager.

Using PHP Manager:

- Register PHP
- Verify PHP is recognized by IIS
</p>
<br />

Step 8: From the “osTicket-Installation-Files” folder, install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
  
During installation:

- Select Typical Setup
- Launch Configuration Wizard (after install) 
- Choose standard configuration
- Create a root username and a root password  

Verify MySQL service is running after installation.

<p>
<img width="872" height="599" alt="install mysql " src="https://github.com/user-attachments/assets/82768547-e349-4132-bc5d-a0a58ac6ac8c" />
</p>
<p>
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

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
