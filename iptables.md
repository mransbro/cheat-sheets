# IPTables


## Viewing information

iptables -L --line-numbers

iptables -L -v

iptables -S



### Append
iptables -A <chain> -s <source> -j <action>

### Remove

iptables -D <chain> <line number>

## Save Changes
/sbin/service iptables save

iptables -F <chain>

iptables -P <chain> <policy>

## Backup and Restore

iptables-save -c > /etc/iptables.rules

iptables-restore > /etc/iptables.rules

iptables -A INPUT -i etho -m state --state RELATED, ESTABLISHED -j ACCEPT