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

- Windows 10 Pro</b> (21H2) x64 Gen2

<h2>List of Prerequisites</h2>

- Setup Resource Group in Azure
- Setup Virtual Machine within Resource Group
- Install / Enable IIS in Windows WITH CGI
- Create the directory C:\PHP and install PHP
- Install osTicket v1.15.8-
- Install HeidiSQL
- Setup osticket in the browser

<h2>Installation Steps</h2>

<p>
1) Setup Resource group within Azure and name it "RG-osTicket".<br>
  Once done, select "Review + Create" button at the bottom to create.<br>
</p>
<p>
<img src="https://i.imgur.com/pRvYuHO.png" height="80%" width="80%" alt="Resource Group"/>
</p>
<br />

<p>
2) Setup Virtual Machine under Resource Group created in step 1.<br>
  Then name the Virtual Machine "osTicket-VM".<br> 
  Make sure to select "Windows 10 Pro" for image.<br>
</p>
<p>
<img src="https://i.imgur.com/CGKUI8T.png" height="80%" width="80%" alt="Virtual Machine Settings"/>
</p>
<br />

<p>
3) Make sure to select a decent size virtual machine.<br>
  Create username and password for this virtual machine.<br> 
  Then select "allow selected ports". Click button "Review + Create".
</p>
<p>
<img src="https://i.imgur.com/4VTW77M.png" height="80%" width="80%" alt="Virtual Machine Settings"/>
</p>
<br />

<p>
4) Use Remote Desktop Connection (Windows) to log into your virtual machine account.
</p>
<p>
<img src="https://i.imgur.com/q4rgaEi.png" height="80%" width="80%" alt="Remote Desktop Connection"/>
</p>
<br />

<p>
5) Install / Enable IIS in Windows WITH CGI <br>
  Control Panel > Programs > Turn Windows features on or off > Internet Information Services > World Wide Web Services > Application Development Features > [X] CGI
</p>
<p>
<img src="https://i.imgur.com/tp9ywAo.png" height="80%" width="80%" alt="CGI"/>
</p>
<br />

<p>
6) Check to make sure it was installed/enabled by opening a new tab within the internet browser and type into the address bar " 127.0.0.1 " indicating that it's running.
 </p>
 <p>
<img src="https://i.imgur.com/AUXAPuv.png" height="80%" width="80%" alt="127.0.0.1"/>
</p>
<br />

<p>
7) Download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi) <br>
Download and install the Rewrite Module (rewrite_amd64_en-US.msi)
<br />
 
<p>
8) Create the directory C:\PHP <br>
Download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP <br>
Download and install VC_redist.x86.exe. <br>
Download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi)<br>
  -Typical Setup -><br>
  -Launch Configuration Wizard (after install) -><br>
  -Standard Configuration -><br>
  -Set Username and Password
</p>
<p>
<img src="https://i.imgur.com/A4w95UB.png" height="80%" width="80%" alt="PHP Install"/>
</p>
<br />

<p>
9) Open IIS (Internet Information Services Manager) as an Admin from Windows Search <br>
Register PHP from within IIS (Php Manager > Register new PHP version > Browse to PHP Folder and execute php-cgi)<br>
Reload IIS (Open IIS, Stop and Start the server/restart) <br>
</p>
<p>
<img src="https://i.imgur.com/LFN0z60.png" height="80%" width="80%" alt="PHP"/>
</p>
<br />

<p>
10) Download osTicket from the Installation Files Folder <br>
Extract and copy “upload” folder to c:\inetpub\wwwroot <br>
Within c:\inetpub\wwwroot, Rename “upload” to “osTicket” <br>
Reload IIS (Open IIS, Stop and Start the server/restart)<br>
</p>
<p>
<img src="https://i.imgur.com/SjhspdM.png" height="80%" width="80%" alt="osTicket"/>
</p>
<br />
 
<p>
11) Go to sites -> Default -> osTicket
On the right, click “Browse *:80”
</p>
<p>
<img src="https://i.imgur.com/WHOLCfT.png" height="80%" width="80%" alt="Start osTicket"/><br>
<img src="https://i.imgur.com/uXuvtuZ.png" height="80%" width="80%" alt="Start osTicket"/><br>
</p>
<br />
  
<p>
12) Note that some extensions are not enabled <br>
Go back to IIS, sites -> Default -> osTicket <br>
Double-click PHP Manager <br>
Click “Enable or disable an extension” <br>
-Enable: php_imap.dll<br>
-Enable: php_intl.dll<br>
-Enable: php_opcache.dll<br>
-Refresh the osTicket site in your browse, observe the changes<br>
<img src="https://imgur.com/xVdrg1M.png" height="80%" width="80%" alt="Extension"/>
</p>
<p>
<br />

<p>
13) Assign Permissions: ost-config.php<br>
-Right click ost-config.php > Properties > Security > Advanced > Disable Inheritance > Remove all inherited permissions from this object. > ADD > Select a principal > type "Everyone" under Enter the object name > Checknames > Okay > [X] Full Control > Okay > Apply
<p>
<img src="https://i.imgur.com/7bfHX4B.png" height="30%" width="30%" alt="Start osTicket"/><br>
<img src="https://i.imgur.com/XR2GqAG.png" height="50%" width="50%" alt="Start osTicket"/><br>
<img src="https://i.imgur.com/uzbMGzb.png" height="50%" width="50%" alt="Start osTicket"/><br>
</p>
<br />

<p>
14) Continue Setting up osTicket in the browser (click Continue)<br>
-Create User
<p>
<img src="https://i.imgur.com/IaJVKSk.png" height="50%" width="50%" alt="Start osTicket"/><br>
</p>
<br />

<p>
15) Download and install HeidiSQL.<br>
-Open Heidi SQL<br>
-Create a new session, root/Password1<br>
-Connect to the session<br>
-Create a database called “osTicket”<br>
  -Right click "Unamed" > Create New > Database > Type in "osTicket" > Okay
<p>
<img src="https://i.imgur.com/AtGNCjd.png" height="50%" width="50%" alt="Start osTicket"/><br>
<img src="https://i.imgur.com/PgdT90y.png" height="70%" width="70%" alt="Start osTicket"/><br>
</p>
<br />

<p>
16) Continue Setting up osticket in the browser.<br>
- MySQL Database: osTicket<br>
- MySQL Username: root (Enter your Username) <br>
- MySQL Password: Password1 (Enter your Password)<br>
- Click “Install Now!”<br>
<p>
<img src="https://i.imgur.com/tR8xG7k.png" height="50%" width="50%" alt="Start osTicket"/><br>
</p>
<br />
<img src="https://i.imgur.com/UgVpUsQ.png" height="50%" width="50%" alt="Start osTicket"/><br>
Congratulations, hopefully it is installed with no errors!
Browse to your help desk login page: http://localhost/osTicket/scp/login.php
<br>
<br>
End Users osTicket URL:
http://localhost/osTicket/ 
