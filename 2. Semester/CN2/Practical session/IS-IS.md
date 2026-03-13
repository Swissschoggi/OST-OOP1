# CLNS (Connectionless Network Service)

| Term | OSI Model | TCP/IP Model |
|-----|-----|-----|
| **Layer 3 Service** | CLNS | No separate formal name |
| **Service Type** | Connectionless | Connectionless |
| **Data-Plane Protocol** | CLNP | IP |
| **Control-Plane Protocols** | IS-IS / ES-IS | OSPF / IS-IS / BGP |
| **Addressing** | NSAP | IP Address |

CLNS is part of the **OSI networking architecture**.  
It defines how connectionless packet delivery works at **Layer 3 (Network Layer)**.

A key conceptual difference:

- **OSI/CLNS:** strict separation between service definition and protocol implementation.
- **TCP/IP:** layers are more **pragmatic and loosely defined**, and protocols often span conceptual layers.

---

# CLNS Protocol Suite

Some CLNS protocols include:

- **CLNP (Connectionless Network Protocol)** – network-layer data transport
- **ES-IS (End System to Intermediate System)** – host ↔ router discovery
- **IS-IS (Intermediate System to Intermediate System)** – router ↔ router routing

Terminology in OSI:

| Term | Meaning |
|----|----|
| **End System (ES)** | A host |
| **Intermediate System (IS)** | A router |

---

# CLNP (Connectionless Network Protocol)

CLNP is the **OSI equivalent of IP**.

It operates at **Layer 3** and provides **connectionless packet forwarding** between systems.

Similarities between **CLNP and IP**:

- Both are **connectionless**
- Both provide **best-effort delivery**
- Both rely on **separate routing protocols** for path calculation
- Both support **fragmentation and reassembly**

Important difference:

- **CLNP uses NSAP addresses**
- **IP uses IP addresses**

CLNP is rarely used directly today, but **IS-IS originally used CLNP for routing information transport**.

---

# ES-IS (End System to Intermediate System)

ES-IS is a **discovery protocol** operating between **hosts and routers** on the same network segment.

Its purpose is similar to **ARP + Router Discovery in IP networks**, but in the OSI model.

Functions:

- Discover **neighboring systems**
- Exchange **addressing information**
- Detect **reachable routers**

Message types:

| Message | Sent by | Purpose |
|---|---|---|
| **ESH (End System Hello)** | Host | Announces presence to routers |
| **ISH (Intermediate System Hello)** | Router | Announces router availability |

This allows hosts to automatically discover routers within a LAN.

---

# IS-IS (Intermediate System to Intermediate System)

IS-IS is a **link-state routing protocol** used to exchange routing information between routers.

Core characteristics:

- Uses **Link State Advertisements (LSPs)**
- Calculates routes with **Shortest Path First (SPF)** (Dijkstra)
- Highly **scalable and stable**
- Widely used in **large ISP networks**

Important architectural detail:

**IS-IS runs directly over Layer 2 (data link)** rather than over IP.

This is why IS-IS packets:

- are **not encapsulated in IP**
- use **Ethernet multicast MAC addresses**
- do **not depend on IP connectivity to form adjacencies**

---

# NSAP (Network Service Access Point)

An **NSAP address** identifies a **network-layer entity**.

It is conceptually similar to an **IP address**, but structured differently.

Important characteristics:

- **Variable length** (up to **20 bytes / 160 bits**)
- **Hierarchical structure**
- Identifies a **system**, not a specific interface
- Used by routing protocols such as **IS-IS**

---

## General NSAP Structure

Typical structure:
AFI | IDI | DSP

Components:

### AFI – Authority and Format Identifier
- Indicates **address format**
- Identifies the **authority that assigned the address**

### IDI – Initial Domain Identifier
- Identifies the **organization or domain**

### DSP – Domain Specific Part
Contains hierarchical addressing within the domain.

It may include:

- **Area ID**
- **System ID**
- **NSEL (Network Selector)**

---

# IS-IS in IP Routing

Although IS-IS was designed for OSI networks, modern deployments use **Integrated IS-IS**.

Integrated IS-IS can carry:

- **CLNP routes**
- **IPv4 routes**
- **IPv6 routes**

Important detail:

Even when routing **IP**, IS-IS still uses **NSAP-based identifiers** internally.

Routers are identified by their **System ID**, derived from the NSAP address.

---

# Security Characteristics

IS-IS packets:

- are **encapsulated directly in Layer 2 frames**
- **not transported over IP**

Therefore an attacker typically must:

- be **physically connected to the same Layer 2 network**
- or have access to the router/switch infrastructure

This makes **remote attacks harder** compared to routing protocols that run over IP.

For additional protection, IS-IS supports:

- **authentication (clear-text or cryptographic)**
- **LSP integrity checking**

---

# IS-IS Areas and Routing Hierarchy

IS-IS uses a **two-level hierarchy** to improve scalability.

Even in pure IP networks, IS-IS **still uses CLNS-style addressing (NSAP)** to identify routers.

Each router belongs to an **area identified by an Area ID**.

Routers can operate as:

- **Level 1 (L1)**
- **Level 2 (L2)**
- **Level 1-2 (L1/L2)**

---

## Level 1 Router

A **Level 1 router** operates **only within a single IS-IS area**.

Characteristics:

- Maintains an **L1 Link State Database (LSDB)** for its area
- Has **no detailed knowledge of other areas**

Adjacency formation:

- During the **Hello process**, routers check if **Area IDs match**
- If they match, an **L1 adjacency** is formed

After adjacency establishment, routers exchange **Level-1 LSPs** containing:

- Directly connected neighbors within the area
- Reachable IP prefixes within the area
- Associated routing metrics

LSPs are **flooded throughout the area**, resulting in every router having an **identical LSDB**.

Each router then runs **SPF** to compute the shortest paths.

Summary:

A Level-1 router has **complete topology knowledge inside its area**, but no detailed knowledge of other areas.

---

## Level 2 Router

A **Level 2 router** performs **inter-area routing**.

Characteristics:

- Forms adjacencies with other **Level 2 routers**
- **Area IDs do not need to match**

After adjacency formation, L2 routers exchange **Level-2 LSPs**, which contain:

- Information about neighboring L2 routers
- Reachable prefixes from their attached areas
- Associated metrics

Each L2 router runs **SPF on the L2 topology**, allowing routing between areas.

---

## Level 1-2 Router

A **Level 1-2 router** performs both roles.

Functions:

- Participates in **Level 1 routing within its area**
- Participates in **Level 2 routing between areas**

Effectively it acts as an **area border router**, enabling communication between IS-IS areas.

---

# IS-IS Addressing Example

Example NSAP: `49.0001.0000.0000.0001.00` 

Structure:

| Part | Description |
|----|----|
| `49` | AFI |
| `0001` | Area ID |
| `0000.0000.0001` | System ID |
| `00` | NSEL |

Important rules:

- Each **node must have a unique System ID**
- All **System IDs must have the same length within the domain**

---

# IS-IS Packets

## Hello Packets (IIH)

Used to:

- establish **neighbor adjacencies**
- maintain **keepalive communication**

Default hello interval: 10 seconds

Holdtime is calculated as:
Hello Interval × Hello Multiplier


If no Hello is received before the holdtime expires, the adjacency is removed.

---

## Link-State Packets (LSP)

LSPs contain the **actual routing information**.

They include:

- Neighbor information
- Reachable prefixes
- Metrics

These packets are **flooded across the routing domain**.

---

## Sequence Number Packets (SNP)

Used to **control and synchronize LSP distribution**.

They ensure routers have a **consistent link-state database**.

Types include:

- **CSNP (Complete SNP)**
- **PSNP (Partial SNP)**

---

# IS-IS Packet Structure

Each IS-IS packet contains:

- A **common header**
- A set of **TLV fields (Type-Length-Value)**

TLVs allow IS-IS to be **easily extended**, which is why it can support:

- IPv4
- IPv6
- Traffic engineering
- MPLS

---

# IS-IS Multicast MAC Addresses

IS-IS uses **Layer 2 multicast addresses**.

| Address | Purpose |
|---|---|
| `01-80-C2-00-00-14` | All Level 1 routers (AllL1ISs) |
| `01-80-C2-00-00-15` | All Level 2 routers (AllL2ISs) |

---

# Pseudonodes

In **multi-access networks (LANs)**, IS-IS uses a **Designated Intermediate System (DIS)**.

The DIS creates a **pseudonode** representing the LAN segment.

Benefits:

- Reduces the number of LSPs
- Reduces flooding overhead
- Improves scalability

### DIS Election

The DIS is selected based on:

1. **Highest interface priority**
2. **Highest SNPA (MAC address)** if priorities tie

Default Cisco interface priority: 64

Important difference from OSPF:

- **IS-IS has no Backup DIS**
- If a higher priority router appears, **a new DIS election occurs immediately**