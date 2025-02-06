# Remote Access and File Transfer
## `ssh`
Secure your critical data and communications between systems, automated applications, and people with defensive cybersecurity. 
Our solutions defend and safeguard your business secrets and access to them - now and in the future.

Connect to remote server via login / password

```
ssh ubuntu@172.30.1.2
```
(To exit type `logout`).

Create a ssh key:

```
ssh-keygen
```

Copy key to remote server:

```
ssh-copy-id ubuntu@172.30.1.2
```

Connect to remote server with ssh key:

```
ssh ubuntu@172.30.1.2
```

## `scp`
The `scp` command allows you to copy files over ssh connections.

This is pretty useful if you want to transport files between computers, for example to backup something. The `scp` command uses the `ssh` command and they are very much alike. 

However, there are some important differences.

How to use SCP

- To copy from a (remote) server to your computer.
- To copy from your computer to a (remote) server.
- To copy from a (remote) server to another (remote) server (the data is transferred directly between the servers; your own computer will only tell the servers what to do).

Create a file:

```
ls > file.txt
```

These options are very useful for a lot of things that require files to be transferred, so let's have a look at the syntax of this command:

```
scp file.txt ubuntu@172.30.1.2:/home/ubuntu
```

Connect to remote server:

```
ssh ubuntu@172.30.1.2
```

Check copied file:

```
ls
```





