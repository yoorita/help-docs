# Monitoring Network Connections 

## `netstat`

`netstat`: Display information about active network connections. netstat is a command-line network utility tool available in most Unix-like operating systems, including Linux.

Setup `apt install net-tools`.

Describe the primary purpose of `netstat`:
- To display information about active network connections.
- To reveal network-related statistics.
- To help troubleshoot network-related issues.

Basic Syntax: `netstat [options]`.

Some common options used with netstat: 

- `-t`: Display TCP connections -> `netstat -t`.
- `-u`: Display UDP connections -> `netstat -u`.
- `-l`: Show listening ports -> `netstat -l`.
- `-n`: Display numeric addresses and ports (avoids DNS resolution) -> `netstat -n`.

`ss` : A **replacement** for `netstat` with more features.

## ss (socket statistics)

The `ss (socket statistics)` tool is a CLI command used to show network statistics. 
The `ss` command is a simpler and faster version of the now obsolete netstat command. 
Together with the ip command, `ss` is essential for gathering network information and troubleshooting network issues.

Syntax:

`ss` OR `ss <option 1> <option 2> <option 3>`

Main options: 

- `-n`, `--numeric`: Do not try to resolve service names.
- `-a`, `--all`: Display both listening and non-listening (for TCP this means established connections) sockets.
- `-l`, `--listening`: Display only listening sockets (these are omitted by default).
- `-e`, `--extended`: Show detailed socket information.
- `-i`, `--info`: Show internal TCP information.
- `-t`: To list TCP connections.
- `-at`: List All TCP Connections.

[Man SS](https://man7.org/linux/man-pages/man8/ss.8.html)

List **connections to a specific destination IP** address with: `ss dst 172.17.0.1`.

To **show process IDs (PID)**, use: `ss -p`.

List the **summary statistics** for connections with: `ss -s`

### Filter Connections

The ss command allows advanced filtering of results and searching for specific ports or TCP states.

### Filter Using TCP States

Filter TCP connections using the TCP predefined states: `ss state` 

For example, to find all listening TCP connections:

`ss -t state listening`

### Filter by Port Number

Filter for a specific destination port number or port name: `ss dst`.

For example:

`ss dst :53512`
`ss dst :ssh`

Combine multiple queries for more advanced filtering. For example, find all connections with a destination port 5228 or source port mysql:

`ss -a dst :5228 `
`ss -a src :ssh`

To show all listening TCP connections, use the following:

`ss -tln`

This command will show all listening TCP connections on the system, along with the corresponding port number and the process ID that is listening on that port.

`ss -tulpn`

## `nload`

`nload` is a command-line tool to keep an eye on network traffic and bandwidth usage in real time. 
It helps you to **monitor incoming and outgoing traffic** using graphs and provides additional information such as the total amount of transferred data and min/max network usage.

### Install nload
On Debian/Ubuntu, `nload` can be installed from the default system repositories as shown.

`apt install nload`

### How to Use nload to Monitor Linux Network Usage
Once you have started nload, you can switch between the devices (which you can specify either on the command-line or which were auto-detected) by pressing the left and right arrow keys:

`nload`

Available Key Shortcuts After running nload, you may use these shortcut keys below:
- Use **left** and **right** arrow keys or `Enter/Tab` key to switch the display to the next network device or when started with the `-m` flag, to the next page of devices.
- Use `F2` to show the option window.
- Use `F5` to save current settings to the user’s config file.
- Use `F6` to reload settings from the config files.
- Use `q` or `Ctrl+C` to quit nload.

Use `-a` period to set the length in seconds of the time window for average calculation (default is 300):

`nload -a 400`

The `-t` interval flag sets the refresh interval of the display in milliseconds (default value is 500). Note that specifying refresh intervals shorter than about 100 milliseconds makes traffic calculation very unprecise:

`nload -ma 400 -t 600`

## iftop
Interface **TOP (IFTOP)** is a real time console-based network bandwidth monitoring tool. Install iftop

`apt install iftop`

Run

`iftop`

## lsof
The **“lsof”** command tool in Linux is one of the many built-in tools that’s super useful for checking out the **“list of open files”**. Yes, the term “lsof” is the abbreviation of the task.

For finding out all the processes that are currently using a certain port, call “`lsof`” with the “`-i`” flag followed by the protocol and port information.

`lsof -i<46><@hostname|host_address> :<service|port>`

For example, to check out all the programs currently accessing port 22 over TCP/IP protocol, run the following command.

`lsof -i TCP:22`

This method can also be used to show all the processes that are using ports within a certain range, for example, 1 to 1000. The command structure is similar to before with a little magic at the port number part.

`lsof -i TCP:1-1000`

Listing network connections The following command will report all the network connections from the current system

`lsof -i`

