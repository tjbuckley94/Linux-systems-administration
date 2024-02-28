# Linux-systems-administration
<h3>Step 1: Ensure/Double Check Permissions on Sensitive Files</h3>
Permissions on /etc/shadow should allow only root read and write access.
Command to inspect permissions:

**ls -l /etc/shadow**


Command to set permissions (if needed):

**sudo chmod 600 /etc/shadow**


Permissions on /etc/gshadow should allow only root read and write access.
Command to inspect permissions:

**ls -l /etc/ghsadow**


Command to set permissions (if needed):

**sudo chmod 600 /etc/gshadow**


Permissions on /etc/group should allow root read and write access, and allow everyone else read access only.
Command to inspect permissions:

**ls -l /etc/group**


Command to set permissions (if needed):

**sudo chmod 644 /etc/group**


Permissions on /etc/passwd should allow root read and write access, and allow everyone else read access only.
Command to inspect permissions:

**ls -l /etc/passwd**


Command to set permissions (if needed):

**sudo chmod 644 /etc/passwd**


<h3>Step 2: Create User Accounts</h3>
Add user accounts for sam, joe, amy, sara, and admin1 with the useradd command.
Command to add each user account (include all five users):

**sudo adduser sam
sudo adduser joe
sudo adduser amy
sudo adduser sara
sudo adduser admin1**


Ensure that only the admin1 has general sudo access.
Command to add admin1 to the sudo group:

**sudo usermod -aG sudo admin1**


<h3>Step 3: Create User Group and Collaborative Folder</h3>
Add an engineers group to the system.
Command to add group:

**sudo addgroup engineers**


Add users sam, joe, amy, and sara to the managed group.
Command to add users to engineers group (include all four users):

**sudo usermod -aG engineers sam
sudo usermod -aG engineers joe
sudo usermod -aG engineers amy
sudo usermod -aG engineers sara**


Create a shared folder for this group at /home/engineers.
Command to create the shared folder:

**sudo mkdir /home/engineers**


Change ownership on the new engineers’ shared folder to the engineers group.
Command to change ownership of engineers’ shared folder to engineers group:

**sudo chown :engineers engineers**


<h3>Step 4: Lynis Auditing</h3>
Command to install Lynis:

**sudo apt install lynis**


Command to view documentation and instructions:

**sudo lynis --help**


Command to run an audit:

sudo lynis audit system


Provide a report from the Lynis output with recommendations for hardening the system.

Screenshot of report output:




<h3>Optional Additional Challenge</h3>
Command to install chkrootkit:

**sudo apt install chkrootkit**


Command to view documentation and instructions:

**sudo chkrootkit --help**


Command to run expert mode:

**sudo chkrootkit -x**


Provide a report from the chrootkit output with recommendations for hardening the system.

Screenshot of end of sample output:


