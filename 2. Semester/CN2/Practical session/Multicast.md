## IP to MAC
1.  Convert the IP address to binary:
		239.5.5.5 = 11101111.00000101.00000101.00000101
2. Apply the multicast MAC prefix:
		00000001.00000000.01011110.0
3. Insert the 23 IP bits:
		00000001.00000000.01011110.00000101.00000101.00000101
4. Convert to hexadecimal
		0100.5E05.0505
The multicast MAC address above is used to transmit tra!c to group 239.5.5.5

## IGMP
Handles membership of multicast groups
IGMPv1 doesnt have a leave message so packets are forwarded until the timer expires.
IGMPv2's major improvements are that it posseses a leave message. This eliminates a lot of unneeded multicast traffic as there is no need to wait for the group to time out.
IGMPv3 introduces source and destination specific filtering.

### IGMP snooping
is a Layer 2 switch feature that listens to multicast traffic and only sends it on ports that have requested it to prevent flooding the entire VLAN with the traffic.
If not enabled multicast will be sent like a broadcast.

## Protocol Independent Multicast – PIM
relies entirely on unicast routing protocols such as static routing, OSPF or IS-IS.
It has three different modes:
- PIM dense mode
- PIM sparse mode
- PIM sparse-dense mode

### PIM dense mode
In dense mode multicast traffic is **pushed** across the entire network until routers that arent interested send **prune** messages.
Dense mode also uses IGMP, it elects a *querier* on every network segment that uses IGMP to see if clients want to be in a multicast group.
Better usable on small networks as the flooding nature produces unnecessary bandwidth usage.

