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

## Operate running systems

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

## Deploy Configure and Maintain Systems

## Manage users and groups

## Manage Security

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

## Manage Security