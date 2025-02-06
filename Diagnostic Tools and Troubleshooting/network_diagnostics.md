# Network Diagnostics
## `netcat`
`netcat` (often abbreviated to `nc`) is a **computer networking utility** for **reading** from and **writing** to network connections using TCP or UDP. 

The command is designed to be a dependable back-end that can be used directly or easily driven by other programs and scripts. At the same time, it is a feature-rich network debugging and investigation tool, since it can produce almost any kind of connection its user could need and has a number of built-in capabilities. 

It is able to perform port **scanning**, **file transferring** and **port listening**.

`nc localhost 22`

(`Ctr+C` for exit).

### Client/Server Connection
A simple client/server connection is between two devices. 

One device acts as a server (listens) while the other acts as a client (connects).

On terminal 1, run the `nc` command in listen mode and provide a port:

`nc -lv 1234`

On terminal 2, run the `nc` command with the IP address of device 1 in terminal 1 and the port:

`nc -v 172.30.1.2 1234`

(To finish type `Ctrl+C`).

### Ping Specific Port on Website
Use **Netcat** as an alternative to the `ping` command to test a specific port to a website. 

For example:

`nc -zv google.com 443 `

### Scanning Ports 
Use the `nc` command to scan for open ports.

`nc -zv 172.30.1.2 22`

### Transfer Files
Netcat allows transferring files through established connections. 

To see how file transfers work, do the following:

- Create a sample file on terminal 1 using the touch command: `touch file.txt`. The command creates an empty text file.
- Create a listening connection on terminal 1 and redirect the file to the `nc` command: `nc -lv 1234 < file.txt`.
- On terminal 2, connect to terminal 1 and redirect the file: `nc -zv 10.0.2.4 1234 > file.txt`
- Confirm the file transfer is complete using the `ls` command.

The output shows the file name, indicating the transfer was succesful.

## iperf
`iperf/iPerf3` is a tool for active measurements of the maximum achievable bandwidth on IP networks. 

It supports tuning of various parameters related to timing, buffers and protocols (TCP, UDP, SCTP with IPv4 and IPv6). 

For each test it reports the bandwidth, loss, and other parameters. This is a new implementation that shares no code with the original *iPerf* and also is not backwards compatible. 

Install

```
apt install iperf
apt install iperf3 -y
Start server on Terminal 1
```
Start server on Terminal 1

```
iperf3 -s
```

Switch to terminal 2 and print next command:

```
iperf3  -c 172.30.1.2
```

This command connecting to host 172.30.1.2, port 5201.

## `nuttcp`
`nuttcp` is another network test tool, similar to `iperf2` and `iperf3`, that has a number of unique features.

`nuttcp` is a network performance measurement tool intended for use by network and system managers. 

Its most basic usage is to determine the raw TCP (or UDP) network layer throughput by transferring memory buffers from a source system across an interconnecting network to a destination system, either transferring data for a specified time interval, or alternatively transferring a specified number of bytes. 

In addition to reporting the achieved network throughput in Mbps, `nuttcp` also provides additional useful information related to the data transfer such as user, system, and wall-clock time, transmitter and receiver CPU utilization, and loss percentage (for UDP transfers).

Install `nuttcp`:

```
apt install nuttcp -y
```

Run server

```
nuttcp -S
```

Run client:

```
nuttcp -i1 172.30.1.2
```

Send 300 Mbps of UDP in bursts of 20 packets for 5 seconds

```
nuttcp -u -Ri300m/20 -i 1 -T5 172.30.1.2
```
