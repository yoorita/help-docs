# Checking Network Interfaces and IP Addresses

The `ip` command in Linux is a powerful and versatile network configuration and management tool. 
It is used for a wide range of networking tasks, including configuring network interfaces, managing routing tables, and monitoring network performance. 
The `ip` command is part of the `iproute2` package and replaces several older networking utilities, making it the go-to tool for network-related tasks on modern Linux systems. 
Here's an overview of some common uses of the `ip` command:

## 1. Display Network Interfaces and Addresses

`ip address show` or `ip addr show` or `ip a`: display information about all network interfaces and their associated IP addresses.

## 2. Configure Network Interfaces

- `ip link set <interface> up`: bring a network interface up (activate it)
- `ip link set <interface> down`: bring a network interface down (deactivate it)
- `ip addr add <ip_address>/<subnet_mask> dev <interface>`: assign an IP address and subnet mask to a network interface
- `ip addr delete <ip_address>/<subnet_mask> dev <interface>`: remove an IP address from a network interface
- `ip route add default via <gateway>`: set the default gateway for routing

## 3. Routing and Static Routes

- `ip route show`: display the routing table, including default and static routes
- `ip route add /<subnet_mask> via dev`: add a static route to the routing table
- `ip route del /<subnet_mask>`: delete a static route from the routing table

## 4. Managing Network Bridge Devices

- `ip link add name <bridge_name> type bridge`: create a network bridge device
- `ip link set dev master <bridge_name>`: add a network interface to a bridge
- `ip link set dev nomaster`: remove a network interface from a bridge

## 5. Tunneling and VPNs

- `ip tunnel add <tunnel_name> mode <tunnel_mode> remote <remote_address> local <local_address>`: create a network tunnel interface.
- `ip tunnel delete <tunnel_name>`: delete a network tunnel interface.

## 6. Quality of Service (QoS)

- `ip link set dev <interface> qlen <queue_length>`: set the length of the transmit queue for a network interface
- `ip link set dev <interface> txqueuelen <queue_length>`: set the transmit queue length for a network interface

## 7. Monitoring Network Statistics

- `ip -s link show <interface>`: display detailed statistics for a network interface
- `ip -s route show`: display statistics for the routing table

## 8. Multicast Configuration

- `ip maddress show`: display multicast addresses
- `ip mroute show`: display multicast routing information

## 9. Policy-Based Routing

- `ip rule add from <source> table <table>`: add a policy-based routing rule
- `ip rule del from <source> table <table>`: delete a policy-based routing rule

## 10. Network Namespace

- `ip netns add <namespace_name>`: create a network namespace
- `ip netns exec <namespace_name> <command>`: run a command within a specific network namespace
- `ip netns list`: list available network namespaces
<br/>
The `ip` command offers a comprehensive set of features for managing various aspects of networking in Linux. It is a versatile tool that can be used for both basic and advanced networking tasks, making it essential for network administrators and Linux users. You can access detailed help and usage information for the `ip` command by running `ip --help` or `man ip` in your terminal.
