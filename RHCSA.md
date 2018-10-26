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

## Deploy Configure and Maintain Systems

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



