<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration - COMING SOON!</h2>


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Azure Tenant
- Subscription
- Resource Group
- Virtual Machine
- Virtual Network
- Subnet

<h2>Installation Steps</h2>


<p>
  
<img src="https://github.com/whitneydawson123/osTicket-prereq/assets/94804621/a417afe9-a102-4df6-a250-c16536cca4c6" height="80%" width="80%" alt="Step #1"/>
<img src="https://github.com/whitneydawson123/osTicket-prereq/assets/94804621/705ab6ae-c4e0-40af-931e-3a8f552b654f" height="80%" width="80%" alt="Step #2"/>

</p>
<p>
Create a Resource Group and a Virtual Machine in Azure. Both the Resource Group and Virtual Machine should be created in the same region. I selected the Windows 10 virtual machine with 4 vCPUs | 16 GB. Make a username and password which will be used to connect the remote desktop in the following step. Then allow it to create a new virtual network (vnet).
</p>
<br />

<p>
<img src="https://github.com/whitneydawson123/osTicket-prereq/assets/94804621/ddf19356-125c-49d8-80e7-8219eb92e4c0" height="80%" width="80%" alt="Step #3"/>
</p>
<p>
Now that the virtual machine has been created, copy the public IP address of the virtual machine and open the remote desktop. And now you will paste the IP address and enter your username and password from the previous step.
</p>
<br />

<p>
<img src="https://github.com/whitneydawson123/osTicket-prereq/assets/94804621/190ea97b-54f0-422f-98eb-65d9330fc70e" height="80%" width="80%" alt="Step #4"/>
</p>
<p>
Now that you are in the virtual machine, you have to Install and enable Internet Information Services (IIS). This is a web server that runs on the Windows operating system. To do this right click windows symbol in the bottom left corner. Hit Run, then type "control" and it will open the control panel. From there go to programs -> turn Windows features on or off -> Internet Information Services. Expand it, then go to World Wide Web Service and expand it -> then expand the application development features then click CGI. CGI is what will let us install the PHP manager
</p>
<br />

<p>
<img src="https://github.com/whitneydawson123/osTicket-prereq/assets/94804621/e6aef613-cc9f-400f-b472-354ce27d3f85" height="80%" width="80%" alt="Step #5"/>
<img src="https://github.com/whitneydawson123/osTicket-prereq/assets/94804621/2ab43b33-0c75-48bd-ab78-872a30b9568d" height="80%" width="80%" alt="Step #7"/>
</p>
<p>
This is the Installation File. Download  and install PHP Manager for IIS, Rewrite Module, and download PHP 7.3.8.
</p>
<br />

<p>
<img src="https://github.com/whitneydawson123/osTicket-prereq/assets/94804621/27f8f99b-3d3b-44ab-a9b7-adf80bef25cc" height="80%" width="80%" alt="Step #8"/>
<img src="https://github.com/whitneydawson123/osTicket-prereq/assets/94804621/3f55862f-b4c6-41ef-bcb1-d84a03463d2d" height="80%" width="80%" alt="Step #9"/>
</p>
<p>
Create the directory C:/PHP. And extract the PHP 7.3.8 file into this new file. Then download and install VC redist and MYSQL. 
</p>
<br />

<p>
<img src="https://github.com/whitneydawson123/osTicket-prereq/assets/94804621/513a2a2d-7511-4148-a3cb-305620b18548" height="80%" width="80%" alt="Step #10"/>
</p>
<p>
From the installation file download MYSQL. Open it and agree. Select the typical setup and install. Select the standard configuration, execute, and finish
</p>
<br />

<p>
<img src="https://github.com/whitneydawson123/osTicket-prereq/assets/94804621/ef3e48c3-faa4-4718-9d0c-4f955ec281ed" height="80%" width="80%" alt="Step #11"/>
</p>
<p>
Search for Internet Information Services (IIS) in the search bar. Run click and hit Run as administrator. 
</p>
<br />

<p>
<img src="https://github.com/whitneydawson123/osTicket-prereq/assets/94804621/81530cf6-a9ca-4fca-baa3-ed40f5218a68" height="80%" width="80%" alt="Step #12"/>
<img src="https://github.com/whitneydawson123/osTicket-prereq/assets/94804621/a7c31ae6-8bb9-4f91-b8ca-e01f2885bafd" height="80%" width="80%" alt="Step #13"/>
</p>
<p>
Open PHP Manager. Under Register New PHP, register the new PHP version, then click browse -> C drive -> PHP -> php-cgi -> ok. Now reload IIS.
</p>
<br />

<p>
<img src="https://github.com/whitneydawson123/osTicket-prereq/assets/94804621/c4295e1e-e11c-43e2-8f63-f1c1c3341242" height="80%" width="80%" alt="Step #14"/>
<img src="https://github.com/whitneydawson123/osTicket-prereq/assets/94804621/c6125640-2cbd-4a76-bc36-b39879d93f65" height="80%" width="80%" alt="Step #15"/>
</p>
<p>
Download the osTicket from the installation file folder. Extract and copy the upload folder to C:\inetpub\wwwroot. Then rename upload to osTicket. <br/> Reload IIS again and then go to sites -> default web site -> osTicket and on the right side click Browse *80 (http)
</p>
<br />

<p>
<img src="https://github.com/whitneydawson123/osTicket-prereq/assets/94804621/feb488b0-be37-4712-85bb-0d2475ee4e64" height="80%" width="80%" alt="Step #16"/>
</p>
<p>
If you see something like this it was successful. Now go back to IIS -> sites -> default website -> osTicket. Click the PHP manager, enable or disable the extension and then enable the following: <br/>
  php_imap.dll <br/>
  php_intl.dll <br/>
  php_opcache.dll <br/>
Then refresh osTicket in your browser.
</p>
<br />

<p>
<img src="https://github.com/whitneydawson123/osTicket-prereq/assets/94804621/183fe327-5c7c-43e0-b0a6-78e2c3ba9e89" height="80%" width="80%" alt="Step #17"/>
</p>
<p>
Go to C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig. Then rename ost-sampleconfig.php to ost-config.php.
</p>
<br />

<p>
<img src="https://github.com/whitneydawson123/osTicket-prereq/assets/94804621/7e0bf44a-b3b7-48dd-ad96-c0aef06f1165" height="80%" width="80%" alt="Step #18"/>
<img src="https://github.com/whitneydawson123/osTicket-prereq/assets/94804621/8b1282f5-aa79-4804-ad78-f4d07e730876" height="80%" width="80%" alt="Step #19"/>
</p>
<p>
Right-click ost-config.php -> Security tab and then click Advanced. Hit disable inheritance, then remove all. Then allow everyone full control. Click continue in the osTicket browser. Name your help, configure the default email, and set up the username and password for logging into osTicket.
</p>
<br />

<p>
<img src="https://github.com/whitneydawson123/osTicket-prereq/assets/94804621/1a625471-ee6f-4347-bc44-727cd87a951c" height="80%" width="80%" alt="Step #20"/>
</p>
<p>
Now, download and install HeidiSQL from the installation folder. Create a new session with the same password and username that you set up your SQL server with and connect.
</p>
<br />

<p>
<img src="https://github.com/whitneydawson123/osTicket-prereq/assets/94804621/1c72550c-8207-4ac9-a19e-272a42785290" height="80%" width="80%" alt="Step #21"/>
</p>
<p>
Right-click Unnamed and created a new database called osTicket. 
</p>
<br />

<p>
<img src="https://github.com/whitneydawson123/osTicket-prereq/assets/94804621/f456bf27-6446-4b01-9688-6cb74837707c" height="80%" width="80%" alt="Step #22"/>
</p>
<p>
Go to the osTicket browser and type in your MYSQL username and password, enter osTicket as the MYSQL Database, and click to install now. You should get a Congratulations page.
</p>
<br />

<p>
<img src="https://github.com/whitneydawson123/osTicket-prereq/assets/94804621/1be00ec5-3e9d-4df6-b98c-9e00a13c6627" height="80%" width="80%" alt="Step #23"/>
</p>
<p>
Now you can log in with your username and password. And if you reach the page, you have completed this project. In the <a href="https://github.com/whitneydawson123/osTicket-post">next part</a>
, the focus will be the post-installation configuration of osTicket
</p>
<br />
