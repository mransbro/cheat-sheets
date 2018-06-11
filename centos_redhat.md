# A Linux Cheat Sheet for Windows Admins

This is a list of Linux commands for Windows Admins to complete common tasks. The list focuses on RedHat/CentOS.

## Task Manager / Performance

```bash
top
```

## Task Manager / Users
Windows Task Manager gives you a quick view on connected and disconnected user sessions. The Linux command alternative is **w**.

``` bash
[root@host01 ~]# w
 10:06:27 up 47 days, 17:11,  1 user,  load average: 0.00, 0.01, 0.05
USER     TTY      FROM             LOGIN@   IDLE   JCPU   PCPU WHAT
root     pts/0    10.10.10.10      09:41    3.00s  0.02s  0.00s w
[root@host01 ~]#
```

## Task Manager / Services

```
service --status-all

service httpd stop

service httpd start
```

## Task Manager / Processes

```bash
ps
ps -e

kill
```

## Copy & Cut a file or directory

Everyone knows with Windows Explorer right click a file or folder and you have the option to copy or cut. Linux uses the **cp** command to copy and the **mv** command to cut.

Both commands have a similar syntax {command} [option] SOURCE DEST.

```bash
cp /web/logs /web/logs/archive

mv log
```

## Delete a file

```bash
rm logfile01.log logfile02.log

rm log*.log
```

## Delete a folder
To delete a directory add the **-r** option

```bash
rm -r /logfiles
```

## User accounts

### List local user accounts

```bash
cat /etc/passwd | awk -F: '{print $1}'
```

## Create a local user

```bash
adduser {username}
passwd {username}
```

## Make a local user administrator

```bash
usermod -aG wheel {username}
```

## Check / Set the time and date

``` bash
date
```

## Install updates

``` bash
yum update
```

## Check disk space

```
df
```

## Search for a file/folder

```
find / -name vmware.conf
```

### Manage firewall

```
iptables -L


```