The Spanning Tree Protocol was made to prevent network loops in Ethernet Networks.
This is done by creating a logical Network topology tree across the network.
STP hereby blocks redundant paths.

**Root Bridge** is the central bridge with the lowest bridge ID. *default is 32768*
**Path Cost** is a metric calculated to determine the shortest path to the root bridge. 
The default path cost is:

| Connection | cost |
| ---------- | ---- |
| 10BaseT    | 100  |
| 100BaseT   | 19   |
| 1000BaseT  | 4    |

The comparison Algorithm looks at:
1. Lowest bridge ID *--> relevant for root bridge election*
2. lowest root path cost
3. lowest sender bridge ID
4. lowest sender port ID

There is exactly:
1 Root bridge
1 Root port per non-root bridge
1 designated port per segment

![[Pasted image 20260115164954.png]]
In this example the Switch A with MAC AAAA.AAAA.AAAA is the root bridge as the ID is the same, the lowest MAC address decides.

Next the **Root ports** are elected, these are the ones from Switch B and C that have the lowest cost to the Root bridge. In this example it's the only ones going from those switches to the Root Bridge. They are always in forwarding state.

After that the **designated ports** are elected. All ports on the root bridge are designated ports.
A designated port is the port within a collision Domain that has the lowest cost to the Root bridge over the non-root port(s).
Every port on the other end of a collision Domain (basically a cable) that has a root port is a designated port.

Every other port now is a **Blocking port**.

#### Broadcast Domains
Broadcast Domains show the limit of a broadcast message, L2 Switches and hubs forward Broadcasts but Routers and L3 Switches do not and hereby limit the Broadcast domain.
#### Collision domain
Collision domains work like a simple link between devices and show where collisions can occur in a network. Hubs count together with end devices as a collision domain, Switches and Routers have a collision domain on each connected Link.