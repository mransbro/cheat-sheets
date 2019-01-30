# Red Hat Certified Systems Administrator Exam Study Notes

Table of Contents
=================

* [Understand and use essential tools](#Understand-and-use-essential-tools)

* [Operate running systems](#Operate-running-systems)

* [Configure Local Storage](#Configure-Local-Storage)

* [Create and Configure File Systems](#Deploy-Configure-File-Systems)

* [Deploy Configure and Maintain Systems](#Deploy-Configure-and-Maintain-Systems)

* [Manage users and groups](#Manage-users-and-groups)

* [Manage Security](#Manage-Security)




## Understand and use essential tools

### Finding Files with locate and find

Locate is a cached search which uses a DB to store file names and locations. A CRON job updates the DB. This means sometimes the updateddb command is needed.
It also also very fast as its cached.

Find isnt as fast but is more flexible.

find / -name 'user-db'
find / -user 'centos'
find /etc/ -mtime -3
useradd mary
id mary
find / -uid 1000 -type f -exec cp /home/marys-files

### Create and Edit Text Files

Nano needs installing

Vi will always been available. Must be learned.

When first entering vi you get placed in command mode
Pressing i enters insert mode

Add vi commands

### Create, Delete, Copy and Move Files and Directories

Touch creates files
touch {file1, file2, file3}

mkdir {dir1, dir2, dir3}

To rename a file or directory use the mv command

mv file1 file1_newname

mkdir -p flag ignores any parent dir errors and creates as needed

Tree is an app that needs installing but it useful for displaying the directory structure

Use the rm command to remove
rm -rf file1

### Create Hard and Soft links

Two types of links in Linx

Symbolic: refers to a path of a file
Hard:  refers to the same inode as the linked file

Sym links can work across file systems, hard links cannot.

ln -s filename linkname

ls -il displays the inode number and also the number of links to a file

### List, set and change standard ugo/rwx permissions


### Locate, Read and Use System Documentation with man, info and /usr/share/doc

The mandb command manuals updates the man db cache.
apropos searches the manpages and descriptions. This is sometimes needed for searches such as passwd where there is more then one level of man page.

Man pages are old and GNU documention is moving over to info
info searches the /usr/share/info

Info will return man pages if there is no info node on a topic
When inside info press ? to view navigation commands

To search info:
info --apropos=tee

/usr/share/doc holds documentation. Look in here if nothing in info or man.

If something is installed via rpm
rpm -qd packagename

## Operate running systems

Interrupting the boot process. This can only be done via the console so not suitable for all virtuilization systems.

### Start, Stop and Check the status of network services

There is a network.service.

Systemctl commands will always assume you mean service if the unit type isnt specified.

systemctl start

systemctl stop

systemctl is-enabled

systemctl status network

### Securely transfer files between servers

SFTP and SCP go over port 22. These are encrypted transfer methods.

```sh
scp <filename> usercreds@host:dir_location
```

```
sftp user@host
get <file>
put <file>
```

### Rebooting and Starting up

Systemd handles the shutting down and starting of our system.

Legacy commands are still available
reboot

systemctl reboot
systemctl halt

halt

shutdown
shutdown -h
shutdown -r
shutdown -P +5 System going down for reboot
shutdown -c
shutdown -r 00:00

Targets used now instead of run levels


## Configure Local Storage

### LVM

LVM 

## Create and Configure File Systems

### Create, mount, unmount, and use vfat, ext4, and xfs file systems
### Mount and unmount CIFS and NFS network file systems
### Extend existing logical volumes
### Create and configure set-GID directories for collaboration
### Create and manage Access Control Lists (ACLs)
### Diagnose and correct file permission problems

## Deploy Configure and Maintain Systems

### Schedule Tasks Using at and cron

Usual process to install and run at

```bash
yum install at
systemctl enable atd
systemct start atd
```

The syntax for at

at now + 5 minutes
at 4am + 2 days

After entering the first command the at prompt will appear.

'''
at> date
'''

To exit the at prompt press crtl+d


## Manage users and groups

/etc/passwd file lists all user accounts on system and info linked to them.
It is colon seperated and contains the following info:
Username:Encrypted Password: User ID number (UID):Users group ID (GID):Full name of the user (GECOS):User's home directory: Login shell

/etc/skel any files in this location get copied to a users home directory when that user is created

/etc/login.defs contains default user config information.

/etc/defaults

/etc/shadow are where the OS stores the users encrypted password

Setting a users shell to /sbin/nologin stops them from logging in

/etc/group contains all groups
getent command returns all groups a user is a member of

### Create, delete and modify local user accounts

### Change passwords and adjust password aging for local user accounts

### Create, delete, and modify local groups and group memberships

### Configure a system to use an exsiting authentication service for user and group information

## Manage Security

### Configure Firewall settings Using Available Firewall Utilities

Net filter is controlled by iptables and firewalld

Firewalld is the prefered Redhat method.
Not installed on minimum installation of RedHat but does come with the base install.

To install firewalld and the firewall graphical interface:

yum install firewalld firewall-config

Firewalld is a service so once installed, needs to be enabled and started

systemctl enable firewalld
systemctl start firewalld

The firewall has the conecpt of changes being permanent or in temporary (runtime).
A runtime change doesnt need the firewall to be reload before working but wont surive a reboot.

Firewalld uses the firewall-cmd command

firewall-cmd state
running

The firewall uses zones to apply predefined rules for network connections. The rules are based on the level of trust for traffic in that network. We trust the traffic on our home network but wouldnt trust traffic on a public connection such as shared public wifi.

To get the default zone
firewall-cmd --get-default-zone

To list all zones
firewall-cmd --get-zones

To check what zone an interface is in
firewall-cmd --get-active-zones

To change the zone an interface is in
firewall-cmd --zone=work --change-interface=eth0

Zones can be given source IP ranges. If our DMZ subnet uses 10.10.11.0/24 we can add that as a source for that zone.
firewall-cmd  --zone=dmz --add-source=10.10.11.0/24

To view all current rules
firewall-cmd --list-all

To view only services
firewall-cmd --list-services

To view only ports
firewall-cmd --list-ports

To enable a service
firewall-cmd --zone=work --add-service=http

To make the change permanent use the -permanent option
firewall-cmd --permanent --zone=work --add-service=http

Once a permanent change is made the firewall must be reload/restarted for the changes to be written to config files and take affect.
systemctl restart firewalld

### Configure Key-based authentication for SSH

