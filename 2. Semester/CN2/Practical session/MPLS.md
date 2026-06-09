Host computers have no awareness of the existence of MLPS.
If a Router adds an MLPS Lable, the next router will check the LFIB and noch check the IT address, and the last router will pop (remove) the label after being forwarded the packet.

The first router is an **ingress PE** router, the last one an **egress PE**router and everything in between a **P** router.

By copying the MPLS TTL field from the previous router, the Service Provider can make sure no router has visibility of its MPLS network.

A label is always associated with an IP prefix.

The LIB essentially holds all the labels and associated information that could possibly be
used to forward packets.

```Cisco
! Control plane RIB:
Router#show ip route
!
! Data plane FIB:
Router#show ip cef
!
! Control plane LIB:
Router#show mpls ldp bindings
!
! Data plane LFIB:
Router#show mpls forwarding-table
```
