# Checking Network Interfaces and IP Addresses

- `ifconfig`: display information about **network interfaces** and **IP addresses**
- `ip`: a more powerful tool for **configuring network interfaces, routing**, and more

# Monitoring Network Connections

- `netstat`: display information about **active network connections**
- `ss`: a replacement for netstat with more features
- `nload`: **monitor network** bandwidth usage in **real-time**
- `iftop`: **monitor network** bandwidth usage by **individual** connections

# Checking DNS Configuration

- `nslookup`: **query DNS** servers for domain name resolution
- `dig`: a more **advanced** tool for **DNS** queries
- `host`: query **DNS** for **hostnames**

# Pinging Hosts and Checking Connectivity

- `ping`: send ICMP echo requests to test network connectivity
- `traceroute` or `traceroute6`: trace the route packets take to reach a destination host
- `mtr`: a combination of ping and traceroute for continuous monitoring

# Configuring Network Settings

- `ifconfig` or `ip`: configure network interfaces, IP addresses, netmasks, and more
- `/etc/network/interfaces`: **configuration file** for network interfaces on **Debian-based** systems
- `/etc/sysconfig/network-scripts/ifcfg-*`: **configuration files** for network interfaces on **Red Hat-based** systems

# Firewall Configuration

- `iptables`: a command-line firewall tool for configuring packet filtering rules
- `ufw`: a user-friendly interface for managing iptables rules
- `firewalld`: firewall management tool for systems using the firewalld service

# Network Diagnostics

- `tcpdump`: capture and analyze network traffic
- `wireshark`: a graphical network protocol analyzer
- `netcat` (`nc`): utility for reading/writing data across network connections
- `telnet`: connect to remote hosts using the Telnet protocol

# Remote Access and File Transfer

- `ssh`: securely access remote systems
- `scp`: securely copy files between systems
- `rsync`: synchronize files and directories between systems

# Network Performance Testing

- `iperf`: **measure network** bandwidth between two systems
- `nuttcp`: network **performance measurement** tool
- `pingplotter`: a graphical tool for **visualizing network latency** and packet loss
