Architecture Overview

1. High-Level Architecture

This project uses a simple two-node lab architecture designed to simulate
real-world attacker and defender roles.
 
 
 
2. Components

 2.1 Attacker System
 - Operating System: Kali Linux
 - Role: Network reconnaissance and validation
 - Tools Used:
  - Nmap
  - tcpdump (for validation from target side)

 2.2 Target System
 - Operating System: Metasploitable2 (Ubuntu 8.04, Legacy)
 - Role: Vulnerable system under defensive hardening
 - Security Control Implemented:
  - Host-based firewall using iptables



3. Network Design

 - Network Type: Host-Only / Internal
 - No internet exposure
 - Direct communication between attacker and target only

 This design ensures:
 - Safe experimentation
 - No risk to external systems
 - Full visibility into traffic flow



4. Security Control Placement

The firewall is implemented directly on the target host (Metasploitable2),
acting as the first line of defense before any application-level interaction.



Control Layering:
1. Network packet filtering (iptables)
2. Service-level controls (implicit via firewall)
3. Logging and monitoring



5. Architectural Goal

The architecture focuses on **attack surface reduction** rather than
vulnerability remediation, demonstrating how exposure control alone can
significantly limit exploitation opportunities on legacy systems.