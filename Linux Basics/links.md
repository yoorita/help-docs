# Hard links

```
ln link.txt hard_link.txt
```

will have the same inode number (refers to the index)

Every command execution = get unique number **PID (Process ID)**

# Soft links

```
ln -s link.txt soft_link.txt
```

haas different inode number (refers to the file names)
