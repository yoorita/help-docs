# Pinging Hosts and Checking Connectivity
## `ping`
`ping` is the primary TCP/IP command used to troubleshoot connectivity, reachability, and name resolution. 

Used without parameters, this command displays Help content. 

You can also use this command to test both the computer name and the IP address of the computer.

⚠️ **Note**: Ping has a *different syntax* for key parameters on *Windows* and *Linux*.

Syntax and help:

`ping -h`

Pinging host by name 5 times:

`ping -c 5 google.com`

Pinging host by IP address 5 times:

`ping -c 5 172.30.1.2`

## `tracert`
The `tracert` command is a **Command Prompt** command that's used to show several details about the path that a packet takes from the computer or device you're on to whatever destination you specify.

You might also sometimes see the tracert command referred to as the trace route command or traceroute command.

Setup:

`apt install traceroute`

Syntax:

`tracert traceroute [ -46dFITnreAUDV ] [ -f first_ttl ] [ -g gate,... ] [ -i device ] [ -m max_ttl ] [ -N squeries ] [ -p port ] [ -t tos ] [ -l flow_label ] [ -w MAX,HERE,NEAR ] [ -q nqueries ] [ -s src_addr ] [ -z sendwait ] [ --fwmark=num ] host [ packetlen ]`

Help about traceroute options:

`traceroute`

Test network:

`traceroute google.com`


## `mtr`
The `mtr` command is a **combination** of `ping` and `traceroute` commands. 

It is a network diagnostic tool that continuously sends packets showing ping time for each hop. It also displays network problems of the entire route taken by the network packets.

Using mtr:

`mtr`
`mtr -t localhost`
`mtr -t google.com`

The `-t` option indicates we want to see the output in the curses-based terminal. 

If we hadn’t used this option, we’d receive output in GUI mode, if possible. 

The numbers change depending on the network activity. 

To quit this curses-based terminal, we could press `q` (quit).

Changing the *Displayed Columns Suppose* we are only interested in the **Snt** and **Avg** columns. We could launch `mtr` with the `-o` option:

`mtr -o 'SA' -t google.com`


## tcpdump
The `tcpdump` utility is a command-line network packet analyser. 

It is absolutely essential for diagnosing networking issues from the server side.

Install

`apt-get install tcpdump`

Syntax 

`tcpdump [ -AdDefIKlLnNOpqRStuUvxX ] [ -B buffer_size ] [ -c count ] [ -C file_size ] [ -G rotate_seconds ] [ -F file ] [ -i interface ] [ -m module ] [ -M secret ] [ -r file ] [ -s snaplen ] [ -T type ] [ -w file ] [ -W filecount ] [ -E spi@ipaddr algo:secret,... ] [ -y datalinktype ] [ -z postrotate-command ] [ -Z user ] [ expression ]`

[More information here](https://www.tcpdump.org/)

To capture packets for troubleshooting or analysis, `tcpdump` requires elevated permissions, so in the following examples most commands are prefixed with sudo.

To begin, use the command `tcpdump --list-interfaces` (or `-D` for short) to see which interfaces are available for capture:

`sudo tcpdump -D`

Let's use it to start capturing some packets. Capture all packets in any interface by running this command:

`sudo tcpdump --interface any`

**Tcpdump** continues to capture packets until it receives an interrupt signal. You can interrupt capturing by pressing `Ctrl+C`.

In this case, since I am connected to this server using `ssh`, `tcpdump` captured all these packets. To limit the number of packets captured and stop `tcpdump`, use the `-c` (for count) option:

`sudo tcpdump -i any -c 5`

Protocol To filter packets based on protocol, specifying the protocol in the command line. For example, capture ICMP packets only by using this command:

`sudo tcpdump -i any -c5 icmp`

In a different terminal, try to ping another machine:

`ping opensource.com`

Back in the `tcpdump` capture, notice that `tcpdump` captures and displays only the ICMP-related packets. 

In this case, `tcpdump` is not displaying name resolution packets that were generated when resolving the name *opensource.com*

Port *To filter* packets based on the desired service or port, use the port filter. 

For example, capture packets related to a web (HTTP) service by using this command:

`sudo tcpdump -i any -c5 -nn port 80`

Complex expressions You can also combine filters by using the logical operators and and or to create more complex expressions. 

For example, to filter packets from source IP address 172.30.1.2 and service SSH only, use this command:

`sudo tcpdump -i any -c5 -nn src 172.30.1.2 and port 22`

In a different terminal, try to connect to another machine via `ssh` (user ubuntu password ubuntu):

`ssh ubuntu@172.30.1.2`

Back in the `tcpdump` capture, notice that `tcpdump` captures and displays.

Checking packet content in the previous examples, we're checking only the packets' headers for information such as **source, destinations, ports**, etc. Sometimes this is all we need to troubleshoot network connectivity issues. Sometimes, however, we need to inspect the content of the packet to ensure that the message we're sending contains what we need or that we received the expected response. 

To see the packet content, `tcpdump` provides two additional flags:
- `-X` to print content in hex, and ASCII.
- `-A` to print the content in ASCII.

For example, inspect the SSH content of a request like this:

`sudo tcpdump -i any -c10 -nn -A port 22`

In a different terminal, try to connect to another machine:

`ssh ubuntu@172.30.1.2`

Back in the `tcpdump` capture, notice that `tcpdump` captures and displays.

### Saving captures to a file
Another useful feature provided by `tcpdump` is the ability to save the capture to a file so you can analyze the results later. 

This allows you to capture packets in batch mode overnight, for example, and verify the results in the morning. It also helps when there are too many packets to analyze since real-time capture can occur too fast.

To save packets to a file instead of displaying them on screen, use the option `-w` (for write):

`sudo tcpdump -i any -c10 -nn -w ssh.pcap port 22`

In a different terminal, try to connect to another machine:

`ssh ubuntu@172.30.1.2`

Back in the `tcpdump` capture, notice that `tcpdump` captures and displays.

`cat ssh.pcap`




