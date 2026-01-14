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
