DHCP manages address assignment in IPv4 (and 6).
It gives out IP addresses from the DHCP server (mostly the router) to clients.
It also gives out other information such as subnet, default gateway and DNS.

If a DHCP is absent devices will assign themselves an APIPA address.

A DHCP server operates as follows:
![[Pasted image 20260114162211.png]]
1. A **DHCP DISCOVERY** is sent from the Client as a Broadcast (to every connected device).
2. The DHCP Server sends a **DHCP OFFER** back, again as a broadcast.
3. The Client reacts with a **DHCP REQUEST**, to Broadcast and says that he likes the offer.
4. The DHCP server sends a last **DHCP PACK** with all the information needed.

### DHCPv6
DHCPv6 works the same as DHCPv4, it has extra features such a Prefix delegation.
It uses UDP.
However DHCPv6 does **NOT USE BROADCAST**!!

### SLAAC
While DHCP is statefull, SLAAC is stateless and does not need a router for address configuration (only for prefix and subnet information).
The Router Advertises the Prefix information and the client generates the Interface identifier that is unique in the subnet. Those two combined form the address of the client.

1. The client creates an `fe80::/10` link local address that is used to communicate on a Link level.
2. Client send a ROUTER DISCOVERY to `ff02::2` (all routers multicast).
3. The Router responds with a RA (**Router Advertisement**) containing network prefix and configuration flags.
4. The Client combines prefix from RA with interface identifier (EUI-64 or random).
5. The client performs a DAD (**Duplicate Address Detection**) by sending a multicast message to the multicast address of the global address it intends to use.


