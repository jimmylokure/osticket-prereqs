<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This lab outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

<h2>Environments and Software</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems</h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Azure VM (Windows 10 Pro Version 22H2 64x)
- <a href="https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD">osTicket Zip Folder</a>
- osTicket v1.15.8 (in folder)
- Rewrire Module 2 (in folder)
- PHP 7.3.8 (in folder)
- PHP Manager for IIS 1.5.0 (in folder)
- HeidiSQL (in folder)
- MySQL 5.5.62 (in folder)
- VC Redistrubal 86x (in folder)
- IIS (Internet Information Services)

<h2>osTicket Installation Lab Steps</h2>

<p>
<img src="https://i.imgur.com/OkLP3jH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
1) Create a Windows 10 Image virtual machine with two vcpus and 8gb of memory. This was done in the Microsoft Azure Portal. 
</p>
<br />

<p>
<img src="https://i.imgur.com/H2SXVAR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
2) After logging in through the Remote Desktop Connection software, I downloaded, and extracted the osTicket Zip Folder within the VM with all the prerequisites to install osTicket.
</p>
<br />

<p>
<img src="https://i.imgur.com/nYDRtHN.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
3) Turn on Internet Information Services (IIS) and CGI from within the control panel "Programs and Features" tab. (Internet Information Services > World Wide Web Services > Application Development Features > CGI)
</p>
<br />

<p>
<img src="https://i.imgur.com/kij51hK.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/YlFyhGa.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>
<p>
4) Next, download the Rewrite Module and PHP Manager for IIS from the extracted osTicket Installation folder.
</p>
<br />

<p>
<img src="https://i.imgur.com/AUz3im9.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/ndAVGQY.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/GStrrqQ.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
5) Create a new directory inside the C drive called "PHP" (C:\PHP) and unzip PHP 7.3.8's contents into that folder.
</p>
<br />

<p>
<img src="https://i.imgur.com/5NTZoHY.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/G5pOVf1.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/6dh9oQa.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>
<p>
6) Download the VC 86x Redistributible and MySQL from the osTicket Installation folder you've extracted. Launch the Instance Configuration Wizard after finishing the installation for MySQL.
</p>
<br />

<p>
<img src="https://i.imgur.com/TMdvdcD.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>
<p>
7) Inside the Instance Configuration Wizard, I chose a memorable user and password for the MySQL database; user is 'root', and the password is 'root', just for the sake of practice within the lab.
</p>
<br />

<p>
<img src="https://i.imgur.com/Shb3gj3.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/Td4e4o4.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/lWcuFQj.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
8) Run IIS as an administrator,open PHP manager and register a new PHP version.
</p>
<br />

<p>
<img src="https://i.imgur.com/Lv9i7Cg.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<p>
9) Locate the php-cgi executable file in the new PHP directory in the C drive for the PHP path, (C:\PHP\php-cgi.exe). Then you need to stop and start IIS.
</p>
<br />

<p>
<img src="https://i.imgur.com/xscH7Rf.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<p>
10) From the osTicket Installation folder, extract osTicket v1.15.8, and copy the 'upload' folder into 'C:\inetpub\wwwroot'. IMPORTANT, you must rename the new copied 'upload' folder in this directory to 'osTicket'. Then we can stop and start IIS again.
</p>
<br />

<p>
<img src="https://i.imgur.com/1KSIKTl.png" height="30%" width="30%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/kEDL7zD.png" height="30%" width="30%" alt="Disk Sanitization Steps"/>
</p>
<p>
11) Inside the left side of IIS, browse to Sites > Default Web Site > osTicket, then hit "Browse *:80 (http) on the right side of the folder details.
  We're also going to enable the extensions within osTicket's 'PHP Manager'. 
  Click 'enable or disable an extenstion', then enable these three extensions below:
  'php_imap.dll', 'php_intl.dll', and 'php_opcache.dll'. You can then refresh the osTicket site.
</p>
<br />

<p>
<img src="https://i.imgur.com/o5xLfYG.png" height="30%" width="30%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/4F6XUSM.png" height="30%" width="30%" alt="Disk Sanitization Steps"/>
</p>
<p>
12) Go inside 'C:\inetpub\wwwroot\osTicket\include' and look for the 'ost-sampleconfig.php' file. Rename that same file to 'ost-config.php'.
</p>
<br />
