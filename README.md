# osticket-prereq
![image](https://github.com/user-attachments/assets/a5d8e889-d705-4b62-bd1c-c3dcfa55e5d9)
# How to Install osTicket

This is a straightforward guide to setting up the help desk ticketing system, osTicket.

## Files You Need to Download
- Download Now 📁
  https://drive.google.com/drive/u/2/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6
  
## Software & Technologies Used
- Windows 10 (Build 19044)
- Microsoft Azure (Virtual Machines)
- Remote Desktop (RDP)
- Internet Information Services (IIS)

## Prerequisites
- Create a Virtual Machine in Azure
- Install osTicket v1.15.8
- Install HeidiSQL
- Install MySQL
- Install PHP
- Install Microsoft Visual C++ Redistributable

## Steps

### Create a Virtual Machine in Azure
1. Start by creating a Resource Group in Azure.
2. Create a Windows 10 Virtual Machine (VM) with 2-4 Virtual CPUs. Use any username and password, as these will be used to remote into the VM. Allow Azure to create a new Virtual Network (Vnet).
3. Use the Remote Desktop Connection app on your computer to connect to the VM created in Azure.

### Install / Enable IIS in Windows
1. Go to the Search Bar > Type "Control Panel" > Click "Programs" > "Turn Windows features on or off" > Scroll down to "Internet Information Services (IIS)".
2. Expand "Internet Information Services", then "World Wide Web Services", and finally "Application Development Features". Check the "CGI" option and click OK. CGI is needed to download the PHP Manager, which allows osTicket to run on a web browser.

### Install PHP Manager
1. Download the PHP manager file and agree to the terms. The PHP manager is now installed on your operating system.

### Install Rewrite Module
1. Download the Rewrite Module file, agree to the terms, and install it on your computer.

### Create Directory C:\PHP
1. Open File Explorer, type "C:\" in the search bar, right-click, and create a new folder named "PHP".
2. Download `php-7.3.8-nts-Win32-VC15-x86.zip` from the Files You Need to Download section, extract it, and move the files to the PHP folder you just created.

### VC_REDIST Download
1. Download and install VC_Redist, agreeing to any terms and conditions.

### Download MySQL
1. Download and install MySQL, agreeing to the terms and conditions. Create a username and password for the database that will store the ticket information used in osTicket.

### Install osTicket v1.15.8
1. Download osTicket (download link provided in the lab files).
2. Extract and copy the “upload” folder into `c:\inetpub\wwwroot`.
3. Rename the “upload” folder to “osTicket” within `c:\inetpub\wwwroot`.
4. Reload IIS by opening IIS, stopping, and starting the server.
5. Navigate to Sites -> Default -> osTicket.
6. On the right, click “Browse *:80”.

### Enable Extensions in IIS
1. Some extensions are not enabled by default.
2. Go back to IIS, Sites -> Default -> osTicket.
3. Double-click PHP Manager.
4. Click “Enable or disable an extension”.
5. Enable: `php_imap.dll`, `php_intl.dll`, `php_opcache.dll`.
6. Refresh the osTicket site in your browser to observe the changes.

### Rename Configuration File
1. Rename `C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php` to `ost-config.php`.

### Assign Permissions: ost-config.php
1. Disable inheritance and remove all permissions.
2. Add new permissions for "Everyone" with full control.

### Continue Setting up osTicket in the Browser
1. Click Continue.
2. Name your Helpdesk.
3. Enter the default email (which will receive emails from customers).

### Download and Install HeidiSQL
1. Create a new session with the username "root" and password "Password1".
2. Connect to the session.
3. Create a database called “osTicket”.

### Continue Setting up osTicket in the Browser
1. Enter the MySQL Database: osTicket.
2. Enter the MySQL Username: root.
3. Enter the MySQL Password: Password1.
4. Click “Install Now!”

Congratulations, hopefully, it is installed with no errors!

### Clean up
1. Delete the `C:\inetpub\wwwroot\osTicket\setup` folder.
2. Set the permissions of `C:\inetpub\wwwroot\osTicket\include\ost-config.php` to “Read” only.

### Login to the osTicket Admin Panel
1. Go to `http://localhost/osTicket/scp/login.php`.

Congrats, you've finished installing osTicket!
