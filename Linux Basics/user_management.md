To add user

```
useradd -m someuser
```

To check whether user has been created

```
id someuser
```

To **set/reset** user password

```
passwd someuser
```

To check the connection

```
echo ssh someuser@$(curl -s ifconfig.co)
```

Add user to the **ROOT** group (sudo privileges)

```
usermod-aG sudo someuser
sudo whoami
```

If you want to switch to another user `sv - someuser`

Go to **SUPERUSER**

```
sudo su
```

## Users and groups

```
/etc/passwd
```

```
/etc/shadow
```

```
/etc/group
```

Add a group

```
groupadd devops
```

Add user and change the group

```
useradd -m -g admins steve
```

Scenarios to give the users admin rights
- SUDO
- PowerBroker
- Centrify
...
