# Iptables

Iptables filters packets using predefined chains:

INPUT - Packets destined for the host
FORWARD - Packets passing through the host
OUTPUT - Packets originating from the host

Rules are added in a list to each chain. A packet is checked against each rule starting at the top. If a packet matches a rule the action rules action is taken. If the packet doesnt match any rules the chains default action is taken either ACCEPT or DROP.

## Viewing information

Iptables runs as a kernel level module not a service. To check its loaded:

```bash
lsmod | grep ip_tables
```

```bash
# View the current rules with packet info
iptables -L -v
```

```bash
iptables -S
```


```bash
# Displays the rules in number order. The number can be used to delete the rule.
iptables -L --line-numbers
```


### Append

iptables -A <chain> -s <source> -j <action>

### Remove

iptables -D <chain> <line number>

## Save Changes
/sbin/service iptables save

```sh
# Remove exisiting rules
iptables -F
```

iptables -P <chain> <policy>

## Backup and Restore

```sh
# Backup to file
iptables-save -c > /etc/iptables.rules
```

```sh
# Restore from file
iptables-restore > /etc/iptables.rules
```

iptables -A INPUT -i etho -m state --state RELATED, ESTABLISHED -j ACCEPT