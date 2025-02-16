## List all services which are running OS

```
sudo systemctl list-units -t service
```

(`q` to quit)

```
systemctl status *
```

```
systemctl start *
```

```
systemctl stop *
```

To start the service at the reboot

```
systemctl enable *
```

Don't start along with OS

```
systemctl disable *
```
