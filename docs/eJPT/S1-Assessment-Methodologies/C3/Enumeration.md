---
title: "Enumeration"
---

### SMB Lesson

#### Discover SMB share and mount it
```powershell
# Learn to use Nmap to scan the target machine and mount the SMB share of the target machine using the Windows File Explorer as well as using the command prompt.

# Checking the IP address.
ipconfig

# Run Nmap scan against the subnet to discover the target machine’s IP address.
# Nmap --open option would show only exposed ports of the live hosts.
nmap 10.2.16.0/20 --open

# Clear the stored session.
net use * /delete
# Mount the target folder.
net use Z: \\10.0.22.92\C$ smbserver_771 /user:administrator
```

```bash
# Your task is to fingerprint the service using the tools available on the Kali machine and run Nmap scripts to enumerate the Windows target machine SMB service.

# Checking the target IP address.
cat /root/Desktop/target

# Ping the target machine to see if it’s alive or not.
# We can observe that the target machine is alive and we have successfully sent and received all five packets.
ping -c 5 10.2.28.180

# Run a Nmap scan against the target IP.
nmap 10.2.28.180

# We have discovered that multiple ports are open. SMB port 445 is also exposed. We will run the Nmap script to list the supported protocols and dialects of an SMB server.
nmap -p445 --script smb-protocols 10.2.28.180

# Running security mode script to return the information about the SMB security level.
# We have tried to access the target SMB server using a guest user and we have received SMB security level information.
nmap -p445 --script smb-security-mode 10.2.28.180

# We have the SMB server credentials i.e administrator:smbserver_771. We will use it with Nmap script to scan the target to discover sensitive information.
# Enumerating the users logged into a system through an SMB share with Nmap script.
# First, we won’t use any credentials to see the output.
nmap -p445 --script smb-enum-sessions 10.2.28.180
# In case guest login is not enabled we can always use valid credentials of the target machine to discover the same information.
nmap -p445 --script smb-enum-sessions --script-args smbusername=administrator,smbpassword=smbserver_771 10.2.28.180

# Enumerating all available shares.
nmap -p445 --script smb-enum-shares 10.2.28.180

# "The IPC$ share is also known as a null session connection. By using this session, Windows lets anonymous users perform certain activities, such as enumerating the names of domain accounts and network shares."

# Scanning all shares using valid credentials to check the permissions.
nmap -p445 --script smb-enum-shares --script-args smbusername=administrator,smbpassword=smbserver_771 10.2.28.180

# Enumerate the windows users on a target machine.
nmap -p445 --script smb-enum-users --script-args smbusername=administrator,smbpassword=smbserver_771 10.2.28.180

# Get information about the server statistics. It uses port 445 and port 139 to fetch the details.
nmap -p445 --script smb-server-stats --script-args smbusername=administrator,smbpassword=smbserver_771 10.2.28.180

# Enumerating available domains on a target machine.
nmap -p445 --script smb-enum-domains --script-args smbusername=administrator,smbpassword=smbserver_771 10.2.28.180

# Enumerating available user groups on a target machine.
nmap -p445 --script smb-enum-groups --script-args smbusername=administrator,smbpassword=smbserver_771 10.2.28.180

# Enumerating services on a target machine.
nmap -p445 --script smb-enum-services --script-args smbusername=administrator,smbpassword=smbserver_771 10.2.28.180

# Enumerating all the shared folders and drives then running the ls command (The ls command is used to list files or directories, similarly dir in windows) on all the shared folders.
nmap -p445 --script smb-enum-shares,smb-ls --script-args smbusername=administrator,smbpassword=smbserver_771 10.2.28.180
```

```bash
# Your task is to fingerprint the service using the tools available on the Kali machine and run the smbmap tool to enumerate the target machine service.

# Checking the target IP address.
cat /root/Desktop/target

# Run a Nmap scan against the target IP.
nmap 10.2.24.213

# We have discovered that multiple ports are open. SMB port 445 is also exposed. We will run Nmap script to list the supported protocols and dialects of an SMB server.
nmap -p445 --script smb-protocols 10.2.24.213

# We will use the smbmap python script to enumerate the target machine.
# Running smbmap tool to discover all shared folders and drives.
smbmap -u guest -p "" -d . -H 10.2.24.213

# Running smbmap with administrator user credentials.
smbmap -u administrator -p smbserver_771 -d . -H 10.2.24.213

# Execute the command on the target machine through SMB.
smbmap -H 10.2.24.213 -u administrator -p smbserver_771 -x 'ipconfig'

# Listing all drives on the specified host.
smbmap -H 10.2.24.213 -u administrator -p smbserver_771 -L

# List contents of the directory of C:\ drive.
smbmap -H 10.2.24.213 -u administrator -p smbserver_771 -r 'C$'

# We can also upload a file using the smbmap tool if we have the write permission on the shared folder.
# Uploading a sample file.
touch backdoor
smbmap -H 10.2.24.213 -u administrator -p smbserver_771 --upload '/root/backdoor' 'C$\backdoor'
# Verify that the files have been uploaded on the target machine.
smbmap -H 10.2.24.213 -u administrator -p smbserver_771 -r 'C$'

# Download the flag.txt file.
smbmap -H 10.2.24.213 -u administrator -p smbserver_771 --download 'C$\flag.txt'
cat /root/10.2.24.213-C_flag.txt
```