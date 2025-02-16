- `rpm` ([.rpm]) RedHat OS / CentOS use RPM (RedHat Package Manager) 
- `apt`, `apt-get`, `dpkg` ([.dep]) Ubuntu OS (Mint)

## List all the installed packages in your system

```
sudo apt list --installed
```

## All packages available for Linux

```
sudo apt list --all-versions
```

## Install package

```
sudo apt install nginx [-y]
```

`[y]` - avoid interruption for Y/n input

## To remove / erase package

```
sudo apt remove nginx [-y]
```

```
sudo apt autoremove
```

- `apt remove` all binary files og the package but saves file settings
- `apt purge` deletes both the package itself and it's settings files

## To update the complete system

```
sudo apt update -y
```
