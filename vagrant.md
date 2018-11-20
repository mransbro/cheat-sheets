# Vagrant

Vagrant is a tool for building and distributing development environments. It works with various virtualized platforms such as VirtualBox, Hyper-V, VMware, Docker or in the cloud via AWS or OpenStack.

Vagrant uses base images known as boxes to clone and launch virtual machines. Publically avavilable boxes can be found on the Vagrant Cloud catalog.
https://vagrantcloud.com/boxes/search

# Getting started

```bash
# Make a directory
mkdir vagrant_centos7
cd vagrant_centos7
# Running the init command with a box choosen from the catalog will create a single Vagrant box
vagrant init centos/7
# To launch the box run the up command
vagrant up
# To connect to the box
vagrant ssh
```

## Help

```bash
vagrant list-commands
vagrant --help
vagrant <COMMAND> -h
```

## Box

```bash
vagrant box list
```

```bash
# To use a different provider
vagrant up --provider=hyperv
```

```bash
vagrant box add centos/7
```

```bash
vagrant halt
```

```bash
vagrant suspend
```

```bash
vagrant destory
```