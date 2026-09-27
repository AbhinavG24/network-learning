# network-learning
Learning basics of routing with ipv6 and srv6

# Network Learning Journal
 
## Day 1
 
### Environment Setup
 
- Installed WSL2
- Installed Ubuntu 24.04
- Installed iproute2
- Installed tcpdump
 
### Concepts Learned
 
- Namespace
- Veth Pair
- Loopback Interface
- IPv6 Addressing
- Routing Table
- Default Gateway
- Packet Forwarding
 
### Lab 1
 
Topology:
 
h1 ---- r1
 
Learned:
- namespaces behave like virtual computers
- veth pairs behave like virtual cables
- assigned IPv6 addresses
- tested connectivity using ping
 
### Lab 2
 
Topology:
 
h1 ---- r1 ---- h2
 
Learned:
- default route
- packet forwarding
- enabling router functionality
 
### Key Insight
 
A machine with two interfaces is not automatically a router.
IPv6 forwarding must be enabled.
