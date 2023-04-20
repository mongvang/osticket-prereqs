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

<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/pRvYuHO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
1) Setup Resource group within Azure and name it "RG-osTicket".<br>
  Once done, select "Review + Create" button at the bottom to create.<br>
</p>
<br />

<p>
<img src="https://i.imgur.com/CGKUI8T.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
2) Setup Virtual Machine under Resource Group created in step 1.<br>
  Then name the Virtual Machine "osTicket-VM".<br> 
  Make sure to select "Windows 10 Pro" for image.<br>
</p>
<br />

<p>
<img src="https://i.imgur.com/4VTW77M.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
3) Make sure to select a decent size virtual machine.<br>
  Create username and password for this virtual machine.<br> 
  Then select "allow selected ports". Click button "Review + Create".
</p>
<br />
