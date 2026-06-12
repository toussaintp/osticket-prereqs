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
  
A. Create a Windows 10 Virtual Machine in Microsoft Azure.

- Resource Group: osTicket
- Virtual Machine Name: osticket-vm
- Operating System: Windows 10 Pro
- Size: Standard D2s v3 2vcpus
- Username and Password created during deployment

<p>
<img width="871" height="894" alt="Create a Windows 10 Virtual Machine in Microsoft Azure" src="https://github.com/user-attachments/assets/b8280aff-2202-4203-b437-f56972b9aa36" />
</p>
<p>

B. After deployment, connect to the VM using Remote Desktop Protocol (RDP).

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

A. PHP Manager for IIS
<p>
<img width="861" height="682" alt="php manager installed" src="https://github.com/user-attachments/assets/a31e1773-ea2a-4368-88e1-24ffdecf74c4" />
</p>
<p>

B. URL Rewrite Module
<p>
<img width="885" height="700" alt="rewrite installed" src="https://github.com/user-attachments/assets/f54f6307-2c94-4a61-9165-835caff97953" />
</p>
<p>

These components allow IIS to properly run PHP applications such as osTicket.
</p>
<br />

Step 5 - Extract php binaries

A. Create the directory C:\PHP

Go to file explorer -> c: drive -> create folder PHP 

B. From the “osTicket-Installation-Files” folder, unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder

<p>
<img width="878" height="669" alt="extract php binaries" src="https://github.com/user-attachments/assets/d751ec31-0e35-4418-86fc-2323a6ff87e6" />
</p>
<p>
</p>
<br />

Step 6: From the “osTicket-Installation-Files” folder, install VC_redist.x86.exe.

<p>
<img width="872" height="663" alt="visual c installed" src="https://github.com/user-attachments/assets/b588daf9-dc51-4070-a1e5-07a94711cd5e" />
</p>
<p>

This provides required runtime libraries for PHP and other dependencies.
</p>
<br />

Step 7: Install PHP

A. Open IIS Manager (open IIS as an Admin)
 <p>
<img width="870" height="652" alt="php manager admin" src="https://github.com/user-attachments/assets/91e4dd43-8049-447f-9201-7e66ecbf6d67" />
</p>
<p>

B. Using PHP Manager:

- Register PHP (we're making the server aware of the existence of PHP the computer and tell it where it is ):
  double click php manager -> register new php -> click three dots -> find php-cgi in C:PHP
 <p>
<img width="876" height="657" alt="php-cgi" src="https://github.com/user-attachments/assets/7d538cb8-f950-4ba1-a72e-da79768944bc" />
</p>
<p>

C. Verify PHP is recognized by IIS: Reload IIS (Open IIS, Stop and Start the server) … click on osticket-vm (osticket) , right click stop , right click start
 <p>
<img width="876" height="448" alt="reload server" src="https://github.com/user-attachments/assets/b5e71418-3fd9-46c6-a1e1-ea8c8446bbdf" />
</p>
<p>

Step 8: From the “osTicket-Installation-Files” folder, install mysql-5.5.62-win32.msi
  
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

Step 9: Install osTicket v1.15.8
  
A. From the “osTicket-Installation-Files” folder, unzip “osTicket-v1.15.8.zip” to the same folder  

B. Copy the upload folder contents to:

C:\inetpub\wwwroot\osTicket

C. Rename:
upload → osTicket

<p>
<img width="899" height="695" alt="upload to osTicket" src="https://github.com/user-attachments/assets/90232a39-536e-4ecb-9b2f-95fc3b840e88" />
</p>
<p>

D. Restart IIS.

<p>
<img width="876" height="448" alt="reload server" src="https://github.com/user-attachments/assets/b5e71418-3fd9-46c6-a1e1-ea8c8446bbdf" />
</p>
<p>

E. Go to sites -> Default -> osTicket
On the far right, click “Browse *:80”

<p>
<img width="950" height="761" alt="loading osTicket" src="https://github.com/user-attachments/assets/67ba264d-f527-4d3b-a94f-7740a29f5903" />
</p>
<p>

Note that some extensions are not enabled

F. Go back to IIS, sites -> Default -> osTicket -> Double-click PHP Manager -> Click “Enable or disable an extension”

Enable: php_imap.dll -> Enable: php_intl.dll -> Enable: php_opcache.dll

G. Refresh the osTicket site in your browser, observe the changes

<p>
<img width="950" height="764" alt="osTicket enabled" src="https://github.com/user-attachments/assets/339f83b0-9034-4345-a29d-15a7556e2bfd" />
</p>
<p>
  
</p>
<br />

Step 10: Rename: ost-config.php

A. From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

B. Assign Permissions: ost-config.php (right click -> properties -> security -> advanced )

Disable inheritance -> Remove All

Add New Permissions -> select principal -> type Everyone -> check names -> All (full control etc) apply - ok

<p>
<img width="1421" height="736" alt="assign permissions" src="https://github.com/user-attachments/assets/3b413eb2-4f4a-46b4-b6f2-03e47038a776" />
</p>
<p>

Now OSticket has full control of the configuration file

C. Continue Setting up osTicket in the browser (click Continue)

Name Helpdesk

Default email (your email)

Admin user: email address different from default

<p>
<img width="803" height="933" alt="osticket continue set up" src="https://github.com/user-attachments/assets/f21f5c4d-1e60-47e3-9ade-4dcb4d05a632" />
</p>
<p>
</p>
<br />

Step 11: From the “osTicket-Installation-Files” folder, install HeidiSQL. (to make a connection to our database)

A. Install HeidiSQL and launch 

<p>
<img width="693" height="543" alt="heidi installed" src="https://github.com/user-attachments/assets/8a82ab0d-40da-4d67-90d3-fe910335ef48" />
</p>
<p>

B. Connect to MySQL using:

- Create a new session, root/ROOT
- Connect to the session
  
<p>
<img width="791" height="602" alt="root ROOT" src="https://github.com/user-attachments/assets/f091fec1-5e10-4247-8521-dd6cc914964e" />
</p>
<p>

C. Create a database called “osTicket” (right click unamed -> create new -> database-> osTicket) you’ll see that it was created but thre is nothing in it

<p>
<img width="936" height="593" alt="osTicket database" src="https://github.com/user-attachments/assets/82c027e3-cc4f-45cb-b605-cada9e4e2266" />
</p>
<p>

D. Verify successful database connection / finish setting up OS Ticket page 

<p>
<img width="648" height="460" alt="osTicket finish set up" src="https://github.com/user-attachments/assets/e599a27f-a1be-4018-8f62-60150127d484" />
</p>
<p>

<p>
<img width="806" height="646" alt="osTicket completed" src="https://github.com/user-attachments/assets/594e7c1a-085e-40e8-82c7-5b502f8f56d3" />
</p>
<p>

</p>
<br />

<h2>Skills Demonstrated</h2>

- Cloud Computing (Microsoft Azure)
- Virtual Machine Deployment
- Remote Desktop Administration
- Windows Server Concepts
- IIS Web Server Configuration
- PHP Configuration
- MySQL Database Management
- Application Installation and Troubleshooting
- User Permission Management
- Help Desk Ticketing Systems
