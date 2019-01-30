# Yum

## Packages

```bash
# List installed packages
yum list installed
```

```bash
# Search for package
yum search <package>
```

```bash
# Install package
yum install <package>
```

```bash
# Update the OS
yum update
```

```bash
# Display information about a package
yum info <package>
```

```bash
# Remove
yum remove <package>
```

```bash
# Clean cache
yum clean all
```

## Groups

```bash
yum grouplist
```

```bash
yum groupinstall 'Server with GUI'
```

## Repos

```bash
yum repolist
```

```bash
yum repolist all
```

```bash
yum --enablerepo=extras-source/7
```

```bash
yum history
```

rpm