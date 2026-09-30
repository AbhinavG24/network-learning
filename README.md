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

## Day 2
 
### Topology
 
h1 ---- r1 ---- r2 ---- h2
 
### Concepts Learned
 
- Multi-hop routing
- Static routes
- Next-hop forwarding
- Traceroute
- End-to-end packet traversal
 
### Addressing Plan
 
Network A:
h1 <-> r1
2001:db8:1::/64
 
Network B:
r1 <-> r2
2001:db8:2::/64
 
Network C:
r2 <-> h2
2001:db8:3::/64
 
### Key Observations
 
- Hosts use a default gateway when the destination is not on the local network.
- Routers use routing tables to determine the next hop.
- Packet forwarding must be enabled on routers.
- Static routes allow routers to reach networks that are not directly connected.
 
### Traceroute Result
 
Observed path:
 
h1 → r1 → r2 → h2
 
Confirmed packet traversal through both routers using traceroute.
 
### Key Insight
 
A router does not need to know the entire path to the destination.
 
A router only needs to know the next hop to which a packet should be forwarded.


##DAY 3
Next Goal
Learn how packets can travel through multiple possible routes instead of a single fixed path.

Target Topology
    r2
   /  \
h1 -- r1 r4 -- h2 \ / r3

Available Paths
Path A:

h1 → r1 → r2 → r4 → h2

Path B:

h1 → r1 → r3 → r4 → h2

Concepts To Learn
Multiple paths between source and destination
Path selection
Route preference
Load balancing
Failover routing
Traffic engineering
Why This Matters
In previous labs only one route existed:

h1 → r1 → r2 → h2

When only one path exists, there is no routing decision.

With multiple paths available, the network must decide which route packets should follow.

Connection To SRv6
Segment Routing over IPv6 (SRv6) allows a source node to explicitly steer packets through a chosen sequence of routers.

Example:

h1 → r1 → r2 → r4 → h2

or

h1 → r1 → r3 → r4 → h2

This forms the foundation for traffic engineering and fast recovery after failures.
