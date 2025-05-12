<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This guide covers the requirements and step-by-step installation process for the open-source help desk ticketing system, osTicket<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com/watch?v=LOzmM5ZjKi0)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (22H2)

<h2>List of Prerequisites</h2>

- Create your virtual machine in Azure
- Log into the VM using Remote Desktop
- Download the osTicket Installation files and unzip it onto the desktop
- Install/enable IIS in Windows with CGI
- Install PHP Manager for IIS
- Install the Rewrite Module
- Create a directory on the C drive called "PHP"
- Unzip the PHP file, from inside the osTicket file, into the "C:\PHP" folder
- Install "VC_redist.x86"
- Install "mysql-5.5.62-win32"
- Register PHP from within IIS
- Install osTicket v1.15.8
- Load the osTicket Site
- Enable extensions
- Rename "ost-config.php" and assign permissions
- Set up osTicket
- Install Heidi SQL
- Finish setting up osTicket

<h2>Installation Steps</h2>

<p>
<img width="792" alt="Screenshot 2025-05-08 at 11 59 56 AM" src="https://github.com/user-attachments/assets/03a27280-265b-498e-af92-a9ba7b0f5499" />
</p>
<p>
On Azure, type "Virtual Machine", click "create" and then choose "Azure Virtual Machine". In here, create a new resource group and name for it. Then come up with a name for the VM, choose your region, and for image choose "Windows 10 Pro, version 22H2". For size, choose something with 2 vcpus and 8GIB memory. Next, create a username and password. Scroll down and make sure to check the box under licensing. Lastly, click "Review and Create" and then "Create". You've now created a VM. 
</p>
<br />

<p>
<img width="1282" alt="Screenshot 2025-05-08 at 12 28 57 PM" src="https://github.com/user-attachments/assets/b7e10342-e4c7-43e1-85fb-39edd2c75ce0" />
</p>
<p>
Copy the public IP Address of your VM. Open your remote desktop app, click the "+" sign at the top right and click "Add PC". For "PC Name", paste the public IP Address. Choose a name for "Friendly Name". Click "Add" and then double click the PC. Log into it using the username and password you created. Unclick all of the privacy settings that pop up. Now, you are in your VM. 
</p>
<br />

<p>
<img width="570" alt="Screenshot 2025-05-08 at 12 44 10 PM" src="https://github.com/user-attachments/assets/e92c2b2d-a73b-4de0-b32a-7d8463f0580b" />
</p>
<p>
Use this link (https://drive.usercontent.google.com/download?id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD&export=download&authuser=0) to download the osTicket Installation files. It will bring you to this website. Click "Download Anyway". Once done, open your downloads folder and drag the file onto your desktop. Right click it and choose "extract all" then click "Extract". Another folder will appear on your desktop. Keep this one and delete the old one. 
</p>
<br />

</p>
<img width="543" alt="Screenshot 2025-05-08 at 12 55 27 PM" src="https://github.com/user-attachments/assets/d3d174ea-9839-433d-a0e8-cb87954d0f7d" />
</p>
<p>
Click the start menu, type "Control Panel" and open it. Under "Programs" choose "uninstall a program" then click "Turn windows features on or off". Check the box named "Internet Information Services" and expand it. Then, expand "World Wide Web Services" and "Application Development Features". Find "CGI" and check the box. Click "OK" and after it finishes, click "close". 
</p>
<br />

</p>
<img width="682" alt="Screenshot 2025-05-12 at 2 07 04 PM" src="https://github.com/user-attachments/assets/502beb5d-6b61-48a7-a49b-6c4b22372af8" />
</p>
<p>
Click the osTicket file on your desktop and open it. It should look like the above picture. Double click the file that says "PHPManagerForIIS_V1.5.0". Then choose "Next", "I Agree" and "Next" again. On the window that pops up click "yes" and when the installation is complete click "close". 
</p>
<br />

</p>
<img width="682" alt="Screenshot 2025-05-12 at 2 09 13 PM" src="https://github.com/user-attachments/assets/cf05d552-607e-4f38-8b04-c822e8471daf" />
</p>
<p>
In the osTicket file, double click the file that says "rewrite_amd64_en-US". Accept the terms and click "Install". On the Window that pops up choose "Yes". Once the installation is complete, click "finish". 
</p>
<br />

</p>
<img width="678" alt="Screenshot 2025-05-12 at 2 11 08 PM" src="https://github.com/user-attachments/assets/9ad743fd-7706-410b-849c-822881ed83a3" />
</p>
<p>
Go to the file explorer and on the left side, towards the bottom, click on "Windows (C:)". In here, right click and choose "New" and then "Folder". Name the new folder "PHP" and click enter. 
</p>
<br />

</p>
<img width="679" alt="Screenshot 2025-05-12 at 2 13 57 PM" src="https://github.com/user-attachments/assets/e8b294a4-a1b8-4113-9d99-1beda5b85d04" />
</p>
<p>
Back in the osTicket file, right click on the file named "php-7.3.8-nts-Win32-VC15-x86" and click "extract all". Click "Browse", go to the "Windows (C:)" folder and click "PHP". Hit "select" and then "extract". 
</p>
<br />

</p>
<img width="679" alt="Screenshot 2025-05-12 at 2 04 34 PM" src="https://github.com/user-attachments/assets/70aeaaf8-77b9-431e-adfe-24cd1c1435e7" />
</p>
<p>
In the osTicket file, double click the file named "VC_redist.x86". Choose "agree" then "install". On the window that pops up choose "yes" and when complete hit "close". 
</p>
<br />

</p>
<img width="678" alt="Screenshot 2025-05-12 at 2 18 55 PM" src="https://github.com/user-attachments/assets/3f191bd2-6e2f-48bd-9712-07ba0bfadcde" />
</p>
<p>
In the osTicket file, double click "mysql-5.5.62-win32". Click "next", accept the terms and click "next" again. Choose "typical" and then hit "install". On the window that pops up choose "yes". Click "Finish", "yes", "next" and then choose "standard", "next" and "next" again. For "new root password", choose a secure username and password that you will remember. Then click "next" and "execute". Once done, click "Finish". 
</p>
<br />

</p>
<img width="542" alt="Screenshot 2025-05-08 at 1 52 54 PM" src="https://github.com/user-attachments/assets/e0f43ebb-ea6e-4b91-9559-d81f827819e4" />
</p>
<p>
Click the start menu and type "IIS". Click "run as administrator". Once opened, click on "PHP Manager" and then "Register new PHP version". Click on the three dots next to the textbox, go to the "Windows (C:)" folder and choose the file titled "PHP". Find "php-cgi" then click "OK". On the top left, click "osticketvm..." to take you back to the homescreen. Then, on the right hand side under "Manage Server" click "stop", wait a moment for it to stop and then click "start". 
</p>
<br />

</p>
<img width="676" alt="Screenshot 2025-05-12 at 1 29 26 PM" src="https://github.com/user-attachments/assets/4ef16c0d-1ecc-4885-9156-e4a0c665403b" />
</p>
<p>
Back in the osTicket folder, right click on "osTicket-v1.15.8" and choose "extract all" then click "extract". Close the folder that pops up when it is done extracting. In the osTicket folder, you'll see another folder titled the same thing but the difference is, the new one says "File Folder" under "Type" (highlighted in the picture above). Choose this one and open it. There will be two other folders in there titled "scripts" and "upload". Open another tab in file explorer and go to "Windows (C:)", "inetpub", "wwwroot" and copy the "upload" folder into here by dragging it over or just by copying and pasting it. Click "continue" if a window pops up. Right click the "upload" folder you just pasted and rename it to "osTicket". Then, open IIS as an admin again, click "stop" on the right hand side, wait a moment and then click "start". 
</p>
<br />

</p>
<img width="1068" alt="Screenshot 2025-05-12 at 1 36 48 PM" src="https://github.com/user-attachments/assets/a7e9607f-bf4c-482e-adcf-23d99d38d2b9" />
</p>
<p>
Back in IIS as an admin, expand "osTicket-vm...", "sites", default web site" and click "osTicket". Then, on the right hand side under "Manage Folder" click "Browse *:80(http)" and it should load the osTicket site. 
</p>
<br />

</p>
<img width="641" alt="Screenshot 2025-05-08 at 2 42 52 PM" src="https://github.com/user-attachments/assets/c1b3c30f-90ed-4193-b70e-1c050701eb87" />
</p>
<p>
In IIS as an admin, on the left click "sites", "default web sites", "osTicket" and then double click "PHP Manager". At the bottom, click "enable or disable an extension." Then, under the list that are disabled, find "php_imap.dll", "php_intl.dll" and "php_opache.dll". Right click on each and click "enable". Then go back to the osTicket website and refresh it. 
</p>
<br />

</p>
<img width="675" alt="Screenshot 2025-05-12 at 1 45 10 PM" src="https://github.com/user-attachments/assets/42196a35-754b-4642-9230-c2c1688b8ad0" />
</p>
<p>
Go to file explorer, click on "Windows (C:)", "inetpub", "wwwroot", "osTicket", "include" then find "ost-sampleconfig.php", right click it and rename it to "ost-config.php". Right click it and choose "properties" as demonstrated in the above picture. Click "security" at the top and then "advanced". Choose "disable inheritance" and "remove all inherited permissions from this object". Then, click "add" and "select a principle". Type who should have permissions and once done select "OK". Check "full control" and click "OK". Click "apply" then "OK". Click "OK" again. 
</p>
<br />

</p>
<img width="937" alt="Screenshot 2025-05-12 at 1 49 52 PM" src="https://github.com/user-attachments/assets/ef531059-ce2d-4c25-b9be-67c84b1a17c5" />
</p>
<p>
On the osTicket website, click "Continue" at the bottom and you will see the screen above. Fill out the info. Choose a helpdesk name and put your email. Under "Admin User", put your name and use a different email address. Put a username and password that you would remember. Before you fill out the database section, complete the next step. 
</p>
<br />

</p>
<img width="679" alt="Screenshot 2025-05-12 at 1 55 03 PM" src="https://github.com/user-attachments/assets/4023354f-5c35-4d43-aa05-f93cb83c7073" />
</p>
<p>
Back in the osTicket folder, double click the file titled "HeidiSQL_12.3.0.6589_Setup". Click "yes" to the window that pops up then choose "I accept the agreement" and "next". Hit "next" for everything and then click "Install". Once done click "Finish". On the window that pops up, click "skip". On the session manager screen, at the bottom left click "new". Where it says "user" and "password" type the one you created on the MySQL Server. Click "open". A window will pop up. On the top left, right click where it says "Unnamed", choose "Create New" and click "database". Type "osTicket" for where it says "Name" and then hit "OK". 
</p>
<br />

</p>
<img width="952" alt="Screenshot 2025-05-12 at 2 02 50 PM" src="https://github.com/user-attachments/assets/d583e202-39a3-465c-9424-c0f9d78aeedf" />
</p>
<p>
Back on the osTicket website, under "Database Settings" type "osTicket" for "MySQL database". Then type the username and password you created on the MySQL Server (not the one you just created above). Hit "Install Now". A screen will come up when it's done, as shown above, saying "Congratulations". OsTicket is now installed. 
