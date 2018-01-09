# Salt

https://docs.saltstack.com/en/latest/ref/cli/

## Master

The Salt master daemon, used to control the Salt minions.

```bash
salt-master --version                       # Print the running version of Salt
salt-master --versions-report               # Print the running version of salt and its dependencies
salt-master --help                          # Show the help message
```

## Minions

```bash
salt-run manage.status                      # What is the status of all my minions? (both up and down)
salt-run manage.up                          # Any minions that are up?
salt-run manage.down                        # Any minions that are down?
salt-run manage.alive                       # Show all alive minions
salt '*' test.version                       # Display salt version
salt '*' test.ping                          # Use test module to check if minion is up and responding.
                                            # (Not an ICMP ping!)
```

## Grains

```bash
salt '*' grains.ls                          # List all grains on all minions
salt '*' grains.item os                     # Show the value of the OS grain for every minion
salt '*' grains.item roles                  # Show the value of the roles grain for every minion
salt 'minion1' grains.setval mygrain True   # Set mygrain to True (create if it doesn't exist yet)
salt 'minion1' grains.delval mygrain        # Delete the value of the grain
```

## Keys

Salt-key executes simple management of Salt server public keys used for authentication.

```bash
salt-key -L                                 # List all keys
salt-key -a <key name>                      # Accept the specified public key
salt-key -A                                 # Accept all pending keys
salt-key -r <key name>                      # Reject the specified key
salt-key -R                                 # Reject all pending keys
salt-key -p <key name>                      # Print the specified key fingerprint
salt-key -d <key name>                      # Removing the minion key
```

## Cloud

```bash
salt-cloud -p aws-centos webapp01               # Creates a VM from called webapp01 from the aws-centos profile
salt-cloud -m /srv/salt/cloud-maps/webapp       # Creates the VMs specified in the map file
salt-cloud -d US-webServer-01                   # Destroys the specified VM
salt-cloud -m /srv/salt/cloud-maps/webapp -d    # Destroys the VMs specified in the map file
salt-cloud -m /srv/salt/cloud-maps/webapp -Q    # Queries the status of the VMs in the map file
```

## Commands

```bash
salt '*' cmd.run 'powershell.exe c:\script.ps1'        # Runs a specified PowerShell script on Windows minion
```

## State
```bash
salt 'server' state.apply                       # Apply all states
salt 'server' state.apply installWeb            # Applies the single state named installWeb
salt 'server' state.apply test=TRUE             # View what a state run is going to change before applying that run
salt-call -l Debug state.apply
```