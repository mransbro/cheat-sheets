### Check current mode
getenforce

### Set the mode
setenforce 0 | 1

### List all contexts
semanage fcontext -l
semanage fcontext -l | grep <package>|<directory>

.autorelabel

restorecon


semanage fcontext -a -t httpd_sys_content_t '/<path>(/.*)?'
restorecon -Rv <path>

### remove context
semanage fcontext -d <context>

### Boolean

getsebool -a

setsebool <bool> on