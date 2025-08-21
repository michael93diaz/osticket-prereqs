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

- Microsoft Azure Account
- Azure Virtual Machine
- Installing Windows 10
- Enable IIS in Windows WITH CGI
- Install PHP Manager for IIS
- Install the Rewrite Module 
- Install PHP
- Install MySQL

## Virtual Machine set up.

1. Go to Microsoft Azure Cloud
<img width="1520" height="862" alt="1  Azure platform" src="https://github.com/user-attachments/assets/c9413712-5558-41d9-b766-185edcdd4c71" />


2. Create a resource group

<img width="668" height="476" alt="2  Resorse GRoups" src="https://github.com/user-attachments/assets/22e0e086-62ef-479a-9237-20e6ed9ed992" />

3. Create a Virtual Machine (VM)
<img width="1555" height="554" alt="3  Virtuak Mchine" src="https://github.com/user-attachments/assets/fffe1e81-494f-4c1e-98bc-96fc0b751d26" />

   
4. Connect to the VM with RDP (Remote Desktop Protocol)
<img width="319" height="205" alt="4  Connect with RDP (Remote Desktop)" src="https://github.com/user-attachments/assets/3bc0af19-a8b2-4949-9968-f97781bd6dfe" />

![VM](https://github.com/user-attachments/assets/3277c216-c6dc-4d23-bdfe-b533712987cc)


<h2>osTicket installation Steps</h2>

1. Turn on Internet Information Services
   - Control Panel -> Uninstall Programs -> Turn Windows features on or off 
<img width="728" height="400" alt="1  Internet Information Services" src="https://github.com/user-attachments/assets/7432a81d-bb5a-4604-ba22-8a811a6a54e1" />

 
2. Install / Enable IIS in Windows WITH CGI
   - World Wide Web Services -> Application Development Features -> [X] CGI
<img width="547" height="387" alt="2  CGI" src="https://github.com/user-attachments/assets/3742ff2f-253c-4700-856f-afc02bab6cf4" />

3. Install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)  
<img width="310" height="253" alt="3  PHP" src="https://github.com/user-attachments/assets/d179b498-b988-475e-9d92-6065f18f1a51" />

4. Install the Rewrite Module (rewrite_amd64_en-US.msi)
<img width="306" height="239" alt="4  Rewrite Module" src="https://github.com/user-attachments/assets/544a237e-ceb5-46f0-a28d-099b8436cb14" />

5. Create the directory C:\PHP (A folder in the C drive     
   
6. Unzip the PHP documentation into the “C:\PHP” folder
   
7. Install Microsoft Visual C++
   
8. Install [MySQL 5.5.62]
	- Typical Setup ->
	- Launch Configuration Wizard (after install) ->
	- Standard Configuration ->
	- Username: root
	- Password: root
<img width="308" height="245" alt="8  MySQl" src="https://github.com/user-attachments/assets/2600419c-9d78-4462-86f5-78442870d885" />

9. Open IIS as an Admin
<img width="824" height="489" alt="9  Open IIS" src="https://github.com/user-attachments/assets/d5d22344-cbb4-4ed2-8652-69ba881e46a5" />

10. Register PHP from within IIS (PHP Manager -> C:\PHP\php-cgi.exe)
<img width="578" height="426" alt="10  Register PHP" src="https://github.com/user-attachments/assets/ead345bd-4713-4293-bf5e-82c63b4e5b21" />
   
11. Reload IIS (Open IIS, Stop and Start the server)
   
12. Install osTicket v1.15.8
    - Unzip “osTicket-v1.15.8.zip” and copy the “upload” folder into “c:\inetpub\wwwroot”
    - Within “c:\inetpub\wwwroot”, Rename “upload” to “osTicket”
<img width="416" height="403" alt="12  Install OS tickets" src="https://github.com/user-attachments/assets/420fb993-1a87-4f1f-9fe6-bc383196ed7e" />
 
13. Reload IIS (Open IIS, Stop, and Start the server)
 
14. Go to sites -> Default -> osTicket
    - On the right, click “Browse *:80”
<img width="1106" height="528" alt="14  Open os tickets" src="https://github.com/user-attachments/assets/7a504b69-caea-4718-a15f-d3ed88611bd6" />

15. Rename: ost-config.php
	- From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
	- To: C:\inetpub\wwwroot\osTicket\include\ost-config.php
<img width="434" height="389" alt="15  Rename" src="https://github.com/user-attachments/assets/d5cbaa67-d14b-400a-b816-975e51a56d19" />

16. Assign Permissions: ost-config.php
	- Disable inheritance -> Remove All
	-  New Permissions -> Everyone -> All 
<img width="565" height="368" alt="16  assing permition" src="https://github.com/user-attachments/assets/c1bcdb3a-a848-450d-a899-cc75a4eb20fe" />

17. Continue Setting up osTicket in the browser (click Continue)
    - Name Helpdesk
    - Default email (receives email from customers)
 <img width="518" height="580" alt="17  Continue settings os tickets" src="https://github.com/user-attachments/assets/3b5b5436-63b6-4e34-b28e-3bc0b017a64a" />

18. Install [HeidiSQL].
    - Open Heidi SQL
    - Create a new session, root/root
    - Connect to the session
    - Create a database called “osTicket”
<img width="371" height="287" alt="18  Install HeidiSQL" src="https://github.com/user-attachments/assets/92cacdbb-c174-4135-b6eb-2158474fb4ed" />
<img width="568" height="394" alt="18b  Connect session and create database" src="https://github.com/user-attachments/assets/a851554c-19e5-41c9-b999-197bff5102d1" />

19. Continue Setting up osTicket in the browser
    - MySQL Database: osTicket
    - MySQL Username: root
    - MySQL Password: root
    - Click “Install Now!”

20. Congratulations, hopefully it is installed with no errors!
    - Browse to your help desk login page: [http://localhost/osTicket/scp/login.php](http://localhost/osTicket/scp/login.php)

21. End Users osTicket URL:
    - [http://localhost/osTicket/](http://localhost/osTicket/)**
<img width="508" height="390" alt="20  Os ticket installed" src="https://github.com/user-attachments/assets/f0aca760-3301-4c7b-9cb4-48e3f740d0a9" />


