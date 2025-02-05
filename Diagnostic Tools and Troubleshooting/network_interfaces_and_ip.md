# Checking Network Interfaces and IP Addresses

The `ip` command in Linux is a powerful and versatile network configuration and management tool. 
It is used for a wide range of networking tasks, including configuring network interfaces, managing routing tables, and monitoring network performance. 
The ip command is part of the `iproute2` package and replaces several older networking utilities, making it the go-to tool for network-related tasks on modern Linux systems. 
Here's an overview of some common uses of the ip command:

## Display Network Interfaces and Addresses

ip address show or ip addr show : Display information about all network interfaces and their associated IP addresses.
ip address show
or

ip addr show

or


ip a
Configure Network Interfaces:

ip link set <interface> up : Bring a network interface up (activate it).
ip link set <interface> down : Bring a network interface down (deactivate it).
ip addr add <ip_address>/<subnet_mask> dev <interface> : Assign an IP address and subnet mask to a network interface.
ip addr delete <ip_address>/<subnet_mask> dev <interface> : Remove an IP address from a network interface.
ip route add default via <gateway> : Set the default gateway for routing.
Routing and Static Routes:

ip route show : Display the routing table, including default and static routes.
ip route show
ip route add /<subnet_mask> via dev : Add a static route to the routing table.
ip route del /<subnet_mask> : Delete a static route from the routing table.
4.Managing Network Bridge Devices:

ip link add name <bridge_name> type bridge: Create a network bridge device.
ip link set dev master <bridge_name>: Add a network interface to a bridge.
ip link set dev nomaster: Remove a network interface from a bridge.
5.Tunneling and VPNs:

ip tunnel add <tunnel_name> mode <tunnel_mode> remote <remote_address> local <local_address> : Create a network tunnel interface.
ip tunnel delete <tunnel_name> : Delete a network tunnel interface.
6.Quality of Service (QoS):

ip link set dev <interface> qlen <queue_length> : Set the length of the transmit queue for a network interface.
ip link set dev <interface> txqueuelen <queue_length> : Set the transmit queue length for a network interface.
7.Monitoring Network Statistics:

ip -s link show <interface> : Display detailed statistics for a network interface.

ip -s link show enp1s0
ip -s route show : Display statistics for the routing table.

 ip -s route show
8.Multicast Configuration:

ip maddress show : Display multicast addresses.
ip maddress show
ip mroute show : Display multicast routing information.
ip mroute show
9.Policy-Based Routing:

ip rule add from <source> table <table> : Add a policy-based routing rule.
ip rule del from <source> table <table> : Delete a policy-based routing rule.
10.Network Namespace:

ip netns add <namespace_name> : Create a network namespace.
ip netns exec <namespace_name> <command> : Run a command within a specific network namespace.
ip netns list : List available network namespaces.
ip netns add softserve
ip netns list
The ip command offers a comprehensive set of features for managing various aspects of networking in Linux. It is a versatile tool that can be used for both basic and advanced networking tasks, making it essential for network administrators and Linux users. You can access detailed help and usage information for the ip command by running ip --help or man ip in your terminal.
