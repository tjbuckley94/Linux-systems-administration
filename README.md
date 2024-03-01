# Linux-systems-administration
<h3>Step 1: Ensure/Double Check Permissions on Sensitive Files</h3>
Permissions on /etc/shadow should allow only root read and write access.
Command to inspect permissions:

 &emsp;&emsp;**$ls -l /etc/shadow**


Command to set permissions (if needed):

 &emsp;&emsp;**$sudo chmod 600 /etc/shadow**


Permissions on /etc/gshadow should allow only root read and write access.
Command to inspect permissions:

 &emsp;&emsp;**$ls -l /etc/ghsadow**


Command to set permissions (if needed):

 &emsp;&emsp;**$sudo chmod 600 /etc/gshadow**


Permissions on /etc/group should allow root read and write access, and allow everyone else read access only.
Command to inspect permissions:

 &emsp;&emsp;**$ls -l /etc/group**


Command to set permissions (if needed):

 &emsp;&emsp;**$sudo chmod 644 /etc/group**


Permissions on /etc/passwd should allow root read and write access, and allow everyone else read access only.
Command to inspect permissions:

 &emsp;&emsp;**$ls -l /etc/passwd**


Command to set permissions (if needed):

 &emsp;&emsp;**$sudo chmod 644 /etc/passwd**


<h3>Step 2: Create User Accounts</h3>
Add user accounts for sam, joe, amy, sara, and admin1 with the useradd command.
Command to add each user account (include all five users):

 &emsp;&emsp;**$sudo adduser sam  
 
 &emsp;&emsp;$sudo adduser joe  
 
 &emsp;&emsp;$sudo adduser amy  
 
 &emsp;&emsp;$sudo adduser sara  
 
 &emsp;&emsp;$sudo adduser admin1**  
 


Ensure that only the admin1 has general sudo access.
Command to add admin1 to the sudo group:

 &emsp;&emsp;**$sudo usermod -aG sudo admin1**


<h3>Step 3: Create User Group and Collaborative Folder</h3>
Add an engineers group to the system.
Command to add group:

 &emsp;&emsp;**$sudo addgroup engineers**


Add users sam, joe, amy, and sara to the managed group.
Command to add users to engineers group (include all four users):

 &emsp;&emsp;**$sudo usermod -aG engineers sam  
 
 &emsp;&emsp;$sudo usermod -aG engineers joe  
 
 &emsp;&emsp;$sudo usermod -aG engineers amy  
 
 &emsp;&emsp;$sudo usermod -aG engineers sara**  
  


Create a shared folder for this group at /home/engineers.
Command to create the shared folder:

 &emsp;&emsp;**$sudo mkdir /home/engineers**


Change ownership on the new engineers’ shared folder to the engineers group.
Command to change ownership of engineers’ shared folder to engineers group:

 &emsp;&emsp;**$sudo chown :engineers engineers**


<h3>Step 4: Lynis Auditing</h3>
Command to install Lynis:

 &emsp;&emsp;**$sudo apt install lynis**


Command to view documentation and instructions:

 &emsp;&emsp;**$sudo lynis --help**


Command to run an audit:

&emsp;&emsp;**$sudo lynis audit system**


Provide a report from the Lynis output with recommendations for hardening the system.

Screenshot of report output:

&emsp;&emsp;![Linux_Admin_1](https://github.com/tjbuckley94/Linux-systems-administration/assets/124013280/2f5b9e27-6a38-4920-bcc9-e80b15d1f305)
![Linux_admin_2](https://github.com/tjbuckley94/Linux-systems-administration/assets/124013280/d5a202ec-7b1f-4380-82c1-3ff794065b73)
![Linux_admin_3](https://github.com/tjbuckley94/Linux-systems-administration/assets/124013280/2c8789cc-9edd-454f-973e-80d7bfa00854)
![Linux_admin_4](https://github.com/tjbuckley94/Linux-systems-administration/assets/124013280/9563a304-49d3-4604-8206-baba27ae7726)
![Linux_admin_5](https://github.com/tjbuckley94/Linux-systems-administration/assets/124013280/931ba78b-1ceb-4851-939e-abd34efcbdc4)



<h3>Optional Additional Challenge</h3>
Command to install chkrootkit:

 &emsp;&emsp;**$sudo apt install chkrootkit**


Command to view documentation and instructions:

 &emsp;&emsp;**$sudo chkrootkit --help**


Command to run expert mode:

 &emsp;&emsp;**$sudo chkrootkit -x**


Provide a report from the chrootkit output with recommendations for hardening the system.

Screenshot of end of sample output:


![Linux_admin_6](https://github.com/tjbuckley94/Linux-systems-administration/assets/124013280/03624719-df86-4c11-8004-b02e472df7a6)
