ARP is a **Layer 2 protocol** that maps **IP addresses (Layer 3)** to **MAC addresses (Layer 2)** on a local network. It's the "phone book" that translates between logical IP addresses and physical hardware addresses.

ARP table: each IP node (host, router) on LAN has table.

If a device needs an entry into its ARP table it sends a broadcast.
The reply will be a unicast to the device that requested the IP or MAC.
