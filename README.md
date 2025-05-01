🛡️ Users, Administrators, Groups and Permissions
A simple user and permission management system including administrators, user groups, and role-based access control (RBAC).
Includes practical examples for:

creating and managing users

working with groups

modifying file and folder permissions in Windows and Linux

📋 Contents
🔧 Local Users and Groups (Windows)

🐧 User Management in Linux

🔐 Permissions in Linux

🪟 Permissions in Windows (ICACLS)
🔧 Local Users and Groups (Windows)
Get-LocalUser
Get-LocalGroup
Get-LocalGroupMember

net user andrea * /add
net user andrea /logonpasswordchg:yes
net user cesar pa5sw0rd /add /logonpasswordchg:yes
net user andrea /del

Remove-LocalUser cesar
🐧 User Management in Linux
cat /etc/sudoers
sudo cat /etc/sudoers
sudo su -

cat /etc/group
cat /etc/passwd

sudo useradd juan
sudo userdel juan

passwd cindy
sudo passwd -e victor
🔐 Permissions in Linux
ls -l ~/my_file
ls -l my_cool_file
chmod u+x my_cool_file
chmod u-x my_cool_file
chmod ugo+r my_cool_file
chmod 754 my_cool_file

sudo chown devan my_cool_file
sudo chgrp best_group_ever my_cool_file
ls -ld /tmp

# Sticky, SetUID, SetGID
sudo chmod u+s my_cool_file
sudo chmod 4755 my_cool_file
sudo chmod g+s my_cool_file
sudo chmod 2755 my_cool_file
sudo chmod 1755 my_folder/
Folder Access Examples:
cd ../qwiklab/documents
ls -l important_document
sudo chmod 700 important_document

ls -ld secret_folder/
sudo chmod u+x secret_folder/
sudo chmod g+w secret_folder/
sudo chmod g-r secret_folder/
sudo chmod o-r secret_folder/
sudo chmod 720 secret_folder/
Ownership Example:
sudo chown cook /home/qwiklab/taco
Permissions in Windows (ICACLS)
icacls C:\Users\cindy\Desktop\
icacls /?

mkdir C:\Windows\Temp\example
icacls C:\Windows\Temp\example >> icacls.txt

ICACLS C:\Users\Qwiklab\Documents\important_document
ICACLS C:\Users\Qwiklab\Documents\important_document /remove "Kara"
ICACLS C:\Users\Qwiklab\Documents\important_document /grant "Kara:(r)"

ICACLS C:\Users\Qwiklab\Secret\ /grant "Phoebe:(r)"
ICACLS C:\Users\Qwiklab\Secret\ /grant "Kara:(w)"

ICACLS C:\Users\Qwiklab\Music\ /remove "Everyone"
ICACLS C:\Users\Qwiklab\Documents\not_so_important_document /grant "Authenticated Users:(w)"
ICACLS C:\Users\Qwiklab\Documents\public_document /grant "Everyone:(r)"
✅ Examples: Combined Permission Edits
# Linux
ls -l not_so_important_document
sudo chmod u+x not_so_important_document
sudo chmod g+w not_so_important_document
sudo chmod a+r not_so_important_document

ls -l public_document
sudo chmod 777 public_document

