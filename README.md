# bugalertUpdate
Script to manually download and update CVP Bugalert database

A Python script for updating the AlertBase.json file on CVP when the CVP cannot access 
the internet directly but a jump host is available which can access the internet and CVP.
Script can be run manually, or using a scheduler to automatically check www.arista.com
for database updates for the CVP Bugalerts feature. A local copy of the AlertBase-CVP.json
file will be left in the directory with the script, it is recommended to leave this file in
place as the script will compare this local copy to the latest downloaded one and if they are
the same then no further action will be taken. The script can also be used to just download 
the latest version of the file without uploading to CVP using the --downloadonly option.
To learn more about BugAlerts see: https://eos.arista.com/eos-4-17-0f/bug-alerts/
INSTALLATION
1. python3 needs to be installed on the jump host
2. pip3 install scp paramiko
3. wget https://github.com/Sparky-python/Arista_scripts/blob/master/bugalertUpdate.py
4. run the script with.. ./bugalertUpdate.py --api <BUGALERTS TOKEN FROM ARISTA.COM> [--cvp 
<CVP SERVER IP ADDRESS> --rootpw <ROOT PASSWORD OF CVP SERVER>] [--downloadonly]
Credit to Corey Hinds for original script which this was based on to update BugAlerts file 
in CVX
