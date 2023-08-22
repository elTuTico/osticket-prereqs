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

- Enabled Internet Information Service (IIS)
- Installed PHP Manager for Web Platform acesss to IIS
- Installed MySQL
- Installed C++ Redistributable 
- Configured permisions and installed osTicket

<h2>Installation Steps</h2>

<p>
<img src="https://github.com/elTuTico/osticket-prereqs/assets/137955237/0cc4d229-d0c3-4971-b620-daa609aef893.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
IIS is essentially a web server that allows this virtual computer to host websites; which would permit osTicket to run off of the computers. To do so you first must enable the computer to have such host capabilities through its Control Panel Programs and Features. Navigate to "Windows Features On or Off'' and scroll down through the list for Internet Information Services. Check the box for IIS, expand its drop down menu, and proceed to check off Web Management Tools->IIS Management Console, World Wide Web Services-> Application Development Features-> CGI, World Wide Web Services-> Application Development Features-> All of Common HTTP Features. Click OK and wait for the install to finish. 
</p>
<br />

<p>
<img src="https://github.com/elTuTico/osticket-prereqs/assets/137955237/d9297635-01f7-4ea1-9ea9-c2e277a36040"/>
</p>
<p>
Test that the installation of IIS was done properly by opening up a web browser and typing in 127.0.0.1. This IP Address is the local host or the loop back that essentially tries to load a webpage running off of the computer itself. It should load up a Windows page like the one shown above. If it does not uninstall the IIS and repeat the previous step over again. 
</p>
<br />

<p>
<img src="https://github.com/elTuTico/osticket-prereqs/assets/137955237/ec8b2888-5753-4154-9353-48648756d46b"/>
</p>
<p>
Proceed by downloading and installing PHP Manager for IIS. Along with the Rewrite Module which allows the special configuration of osTicket’s config files to utilize URLs for behind the scenes tasks. 
</p>
<br />

<p>
<img src="https://github.com/elTuTico/osticket-prereqs/assets/137955237/93c6f8d8-e940-4627-b26b-15be4db8f6d2"/>
</p>
<p>
Create a directory for the PHP files on the local hard drive of the computer by creating a PHP folder on the (C:) Drive itself. Download the PHP zip files that will all be extracted into the PHP folder within the (C:) Drive.
</p>
<br />

<p>
<img src="https://github.com/elTuTico/osticket-prereqs/assets/137955237/5b53dc8a-5cce-4951-b477-2eb15e4648e9"/>
</p>
<p>
Download and install the VC++ Redistributable; a tool required by PHP to function on the back end. 
</p>
<br />

<p>
<img src="https://github.com/elTuTico/osticket-prereqs/assets/137955237/95749c98-3d42-424d-9d21-0bb431dd8fd5"/>
</p>
<p>
Follow up with downloading and installing MySQL server. For the “Choose Setup Type” select “Typical Setup”. Allow the MySQL Instance Configuration Wizard to open upon launch and select “Standard Configuration”. To simplify the last bit make the “new root password” something easy like “Password1” and follow the final prompts. 
</p>
<br />

<p>
<img src="https://github.com/elTuTico/osticket-prereqs/assets/137955237/2594f1b7-bee1-43d6-b993-ec02e712a278"/>
</p>
<p>
Next we’re going to do some configuration inside of IIS. Open up the Start Menu and type IIS. Right click on the program and click “run as administrator”. From here we will be registering PHP Manager by double clicking on it, acknowledging that this is not a registered PHP version, clicking on “register new PHP version”, browse to the PHP folder made on the (C:) Drive, and select the “PHP cgi” found in this folder. All changes to IIS should be followed up with a restart to the server found on the right side of the window found under “Actions”.
</p>
<br />

<p>
<img src="https://github.com/elTuTico/osticket-prereqs/assets/137955237/34c7397b-da2e-43fd-85d8-f7fb8eda644b"/>
</p>
<p>
Now comes the download, installation, and file configuration of osTicket itself. Once you’ve downloaded the zip file of osTicket, extract and copy the “upload” folder into (C:) Drives\inetpub\wwwroot folder. This is a folder that acts like our web server’s main folder, which is why it’s important that the server knows where to go when running osTicket. Which is why we will rename the “upload” folder within wwwroot to “osTicket”.
</p>
<br />

<p>
<img src="https://github.com/elTuTico/osticket-prereqs/assets/137955237/4964ac6c-abb4-40d9-9f6e-1c4854c69ac6"/>
</p>
<p>
Reload the server by opening up IIS as an administrator again and clicking restart. Under “Connections” on the left side of the window drop down from your computer, drop down Sites, drop down Default Web Sites, and lastly click on osTicket. On the right side of the screen click on “Browse *:80” which will open up a new web browser displaying your localhost osTicket setup screen. Upon which there should be a handful of extensions that are not enabled. 
</p>
<br />

<p>
<img src="https://github.com/elTuTico/osticket-prereqs/assets/137955237/d9297635-01f7-4ea1-9ea9-c2e277a36040"/>
</p>
<p>
To enable those extensions head back to your IIS window and head back to the drop down for Site, Default, and double click on osTicket. From there double click on PHP Manger and open up “Enable or disable an extension”. Go ahead and enable php_imap.dll, php_intl.dll, and php_opcache.dll. Finish it off by refreshing the osTicket site in your browser and observe the changes. 
</p>
<br />

<p>
<img src="https://github.com/elTuTico/osticket-prereqs/assets/137955237/d9297635-01f7-4ea1-9ea9-c2e277a36040"/>
</p>
<p>
Test that the installation of IIS was done properly by opening up a web browser and typing in 127.0.0.1. It should load up a Windows page like the one shown above. If it does not uninstall the IIS and do step one over again. 
</p>
<br />

<p>
<img src="https://github.com/elTuTico/osticket-prereqs/assets/137955237/d9297635-01f7-4ea1-9ea9-c2e277a36040"/>
</p>
<p>
Test that the installation of IIS was done properly by opening up a web browser and typing in 127.0.0.1. It should load up a Windows page like the one shown above. If it does not uninstall the IIS and do step one over again. 
</p>
<br />

<p>
<img src="https://github.com/elTuTico/osticket-prereqs/assets/137955237/d9297635-01f7-4ea1-9ea9-c2e277a36040"/>
</p>
<p>
Test that the installation of IIS was done properly by opening up a web browser and typing in 127.0.0.1. It should load up a Windows page like the one shown above. If it does not uninstall the IIS and do step one over again. 
</p>
<br />

<p>
<img src="https://github.com/elTuTico/osticket-prereqs/assets/137955237/d9297635-01f7-4ea1-9ea9-c2e277a36040"/>
</p>
<p>
Test that the installation of IIS was done properly by opening up a web browser and typing in 127.0.0.1. It should load up a Windows page like the one shown above. If it does not uninstall the IIS and do step one over again. 
</p>
<br />
