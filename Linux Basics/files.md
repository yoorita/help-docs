# List files

Syntax `ls <options> <path>`

- `A` hidden files and directories
- `a` hidden files and directories with top path
- `l` list of files with long format
- `c` sort by time
- `d` display directories as if they were regular files
- `f` do not sort directory contents
- `h` human readable
- `i` print **inode** number (serial number)
- `r` sort in reverse

# Work with directories

Current dir `pwd`

Create dir `mkdir dir1 dir2`

Remove empty directories only `rmdir`

Show the content of the file with lines

```
cat -n /etc/passwd
```

Filter the output based on the start line numbers `head`

Filter from the end if the line `tail`

## Filter search

```
grep root /etc/passwd
```

## Filter based on columns

```
awk -F 'delimeter' '{print $column_number}'
```

## Find files

```
find / -name example_name
```

## Browse the content over command line

```
curl
```

## Pipes

```
command1 | command2
```

`xargs` - in case we need to take an input from the command line

