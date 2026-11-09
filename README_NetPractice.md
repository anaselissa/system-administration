# NetPractice

A hands-on networking project completed as part of the 42 curriculum.

NetPractice consists of 10 progressive exercises built around simulated network topologies. The goal is to make each network function correctly by analyzing and fixing IP addressing, subnet masks, gateways, and routing configurations.

## What I Learned

Through the project, I developed a practical understanding of core networking concepts:

- **IPv4 addressing:** 32-bit addresses, network and host portions, and subnet masks.
- **CIDR and subnetting:** Prefix lengths, subnet ranges, block sizes, network addresses, broadcast addresses, and usable host ranges.
- **Gateways:** How hosts communicate with devices outside their local subnet.
- **Routing:** Routing tables, directly connected networks, static routes, default routes, next hops, and longest prefix match.
- **Network devices:** The roles of routers, switches, and network interfaces.
- **Layer 2 and Layer 3:** MAC addresses and Ethernet frames compared with IP addresses and packet routing.
- **Network troubleshooting:** Reading diagnostic logs, tracing packet paths, and identifying addressing or routing errors.

I also studied the OSI model and the TCP/IP model at a conceptual level, including the roles of the main layers and protocols.

## Practical Skills

By completing the 10 levels, I practiced how to:

- Read and interpret small network topologies.
- Configure IPv4 addresses and subnet masks.
- Calculate subnet boundaries and determine whether hosts belong to the same subnet.
- Choose valid gateway addresses.
- Read routing tables and identify the appropriate route and next hop.
- Trace forward and return paths between hosts.
- Diagnose common configuration issues, including invalid or duplicate IP addresses, missing routes, unreachable gateways, and routing loops.
- Use network logs to investigate failures instead of changing configuration values randomly.

## How NetPractice Works

Each level presents a simulated network with one or more communication goals. Configuration fields must be adjusted until the required communication works.

The training interface provides a connectivity check and diagnostic logs to help identify problems. The project contains 10 levels, progressing through increasingly involved network configurations.

## Key Concepts

| Concept | What it means |
|---|---|
| Network address | Identifies a subnet as a whole |
| Broadcast address | IPv4 address used to reach all hosts in a traditional subnet |
| Subnet mask / CIDR | Defines the network prefix and host portion |
| Default gateway | The router a host uses to reach destinations outside its subnet |
| Routing table | Determines how a router forwards packets |
| Next hop | The next router toward a destination |
| Default route | A fallback route, commonly represented as `0.0.0.0/0` |
| MAC address | Layer 2 address used for local frame delivery |
| IP address | Layer 3 logical address used for network communication |

## Learning Resources

### Arabic

- [Microsoft Learn — Computer Network Fundamentals](https://learn.microsoft.com/ar-sa/training/modules/network-fundamentals/)
- [Microsoft Learn — OSI Model](https://learn.microsoft.com/ar-sa/shows/networking-fundamentals/02)
- [IPv4 Addressing, Subnetting & CIDR — Arabic YouTube video](https://www.youtube.com/watch?v=gdTGopMhzCQ)

### English

- [Cloudflare — What is a Subnet?](https://www.cloudflare.com/learning/network-layer/what-is-a-subnet/)
- [Cloudflare — What is the Network Layer?](https://www.cloudflare.com/learning/network-layer/what-is-the-network-layer/)
- [RFC 1918 — Address Allocation for Private Internets](https://www.rfc-editor.org/rfc/rfc1918)

## Use of AI

I used AI as a learning and review assistant during the project. It helped me:

- Understand networking concepts and clarify unfamiliar terminology.
- Practice subnetting and routing scenarios.
- Analyze NetPractice diagnostic logs and investigate configuration errors.
- Challenge my reasoning with questions and exercises.

The configurations were completed through hands-on work in the NetPractice interface. AI explanations were used as learning support and were reviewed against the behavior of the simulator.

## Project Outcome

Completed all 10 NetPractice levels.

The project strengthened my understanding of IPv4 addressing, subnetting, routing, gateways, and practical network troubleshooting.
