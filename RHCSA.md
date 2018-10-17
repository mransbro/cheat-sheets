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

