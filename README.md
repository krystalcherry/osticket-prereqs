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

- Windows 10 Pro</b> (22H2)

<h2>List of Prerequisites</h2>

- Create VM and Enable Internet Information Services(IIS)
- Install web platformer installer
- Install MySQL and username/password set up
- Install C++ redistributable
- Configure permissions and install osTicket

<h2>Installation Steps (click image to enlarge)</h2>

<p>
<img src="https://github.com/krystalcherry/osticket-prereqs/assets/158524799/a6564ff0-cb32-491d-aeb5-6b9346e4a691" height="60%" width="60%" alt="create vm"/>
</p>
<p>
Create virtual machine(VM) using Azure and connect to the VM by using Remote Desktop Conncetion (RDC). 
</p>
<br />
<p>
<img src="https://github.com/krystalcherry/osticket-prereqs/assets/158524799/dcfc9893-32aa-486a-b15b-8679b6d8ea30" height="60%" width="60%" alt="IIS"/>
</p>
<p>
Install and enable IIS on the VM by going to Control Panel -> Programs -> Turn Windows features on or off -> Internet Information Services and make sure everything is selected and under World Wide Web Services selected CGI ubder Application Development Features and under Common HTTP Features checked every box to ensure PHP Manager can be registered later.
</p>
<br />
<p>
<img src="https://github.com/krystalcherry/osticket-prereqs/assets/158524799/5b653978-7180-4744-adf0-d567e86b1cd8" height="60%" width="60%" alt="install phpiis"/>
</p>
<p>
After installing PHP Manager for IIS and Rewrite Module, create a folder on C drive naming it PHP and download and extract PHP to that folder
</p>
<p>
<img src="https://github.com/krystalcherry/osticket-prereqs/assets/158524799/efe17ae6-5658-4221-bb3f-aba4ee898a84" height="60%" width="60%" alt="install mysql"/>
</p>
<p>
Install C++ redistributable and MySQL. Configure MySQL(Typical/Standard)
</p>
<p>
<img src="https://github.com/krystalcherry/osticket-prereqs/assets/158524799/7826986f-4c89-48b4-8ab3-d5a7f3d20759" height="60%" width="60%" alt="install osTicket"/>
</p>
<p>
As admin register PHP in IIS. Download osTicket, extract and copy “upload” folder to c:\inetpub\wwwroot, then within c:\inetpub\wwwroot, Rename “upload” to “osTicket”
</p>
<p>
<img src="https://github.com/krystalcherry/osticket-prereqs/assets/158524799/0f700d95-5452-48ce-9cfc-b528c4faf52f" height="60%" width="60%" alt="browser check1"/>
</p>
<p>
In IIS go to sites -> Default -> osTicket and on the right, click “Browse *:80” and the above should open
</p>
<p>
<img src="https://github.com/krystalcherry/osticket-prereqs/assets/158524799/898175e5-d480-4eb2-b42f-830909b5fcdc" height="60%" width="60%" alt="browser check2"/>
</p>
<p>
In IIS enable extensions php_imap.dll, php_intl.dll and php_opcache.dll then refresh the osTicket site in your browser to check if the extensions now have green check marks
</p>
<p>
<img src="https://github.com/krystalcherry/osticket-prereqs/assets/158524799/abc6f87c-6831-4771-961a-9f22c38cab67" height="60%" width="60%" alt="permissions"/>
</p>
<p>
Rename ost-config.php from C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php to C:\inetpub\wwwroot\osTicket\include\ost-config.php and assign permissions to ost-config.php:
Disable inheritance -> Remove All and New Permissions -> Everyone -> All
</p>
<p>
<img src="https://github.com/krystalcherry/osticket-prereqs/assets/158524799/1afd4dab-9128-4ca8-938f-285724698318" height="60%" width="60%" alt="heidisql"/>
</p>
<p>
From osTicket in browser click Continue and fill out system settings and admin user info. Download and install HeidiSQL to connect to and setup database. Open Heidi SQL. Create and connect to new session using username and password setup during MySQL install. Create a database naming it as you wish.
</p>
<p>
<img src="https://github.com/krystalcherry/osticket-prereqs/assets/158524799/ba2a5a82-84bc-4876-ad9f-88a59ef356d8" height="60%" width="60%" alt="osticket system confirm"/>
</p>
<p>
Then finish setup of osTicket in browser entering the database info clicking to install now resulting in the "Congratulations" screen.
</p>
<p>
<img src="https://github.com/krystalcherry/osticket-prereqs/assets/158524799/62640f76-34da-4343-9964-9836c08d7f98" height="60%" width="60%" alt="admin login"/>
</p>
<p>
Test admin link and login
</p>
<img src="https://github.com/krystalcherry/osticket-prereqs/assets/158524799/43f37d00-1b38-49bf-b436-c2a99da472e8" height="60%" width="60%" alt="cleanup1"/>
</p>
<p>
Test end user link. 
</p>
<p>
<img src="https://github.com/krystalcherry/osticket-prereqs/assets/158524799/cc66c328-462c-42a8-91d1-256196205646" height="60%" width="60%" alt="cleanup2"/>
</p>
<p>
Then perform cleanup by deleting C:\inetpub\wwwroot\osTicket\setup and set Permissions to “Read” only on C:\inetpub\wwwroot\osTicket\include\ost-config.php
</p>
<br />
