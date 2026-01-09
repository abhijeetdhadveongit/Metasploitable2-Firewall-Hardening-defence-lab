This document explains the logic and security purpose of each iptables rule
used in this project.

1. Default Policies

-P INPUT DROP
-P FORWARD DROP
-P OUTPUT ACCEPT

Explanation:
-All inbound traffic is denied by default (default-deny model)
-Forwarding is disabled to prevent routing abuse
-Outbound traffic is allowed to maintain system functionality



2. Loopback Traffic

-A INPUT -i lo -j ACCEPT

Explanation:
-Allows internal system communication
-Required for local services and OS stability
-Does not expose the system externally



3. Established and Related Connections

-A INPUT -m conntrack --ctstate ESTABLISHED,RELATED -j ACCEPT

Explanation:
-Allows return traffic for connections initiated by the host
-Prevents breaking legitimate outbound connections
-Essential for normal system operations



4. ICMP Traffic

-A INPUT -p icmp -j ACCEPT

Explanation:
-Allows basic network diagnostics (ping)
-Confirms host availability
-Does not expose application services



5. Logging Rule

-A INPUT -j LOG --log-prefix "DROP_INPUT: "

Explanation:
-Logs all dropped packets
-Enables detection of scanning activity
-Supports forensic analysis and monitoring



7. Expected Outcome

-Nmap scans show all ports as filtered
-No SYN-ACK or RST responses are returned
-System remains reachable but non-enumerable

Analysis:
- SYN packets confirm network reachability
- No SYN-ACK responses were sent
- No TCP RST packets were observed

Conclusion:
The absence of responses confirms that packets were silently dropped
by the host-based firewall, validating a stealth firewall configuration.

This behavior directly correlates with Nmap reporting ports as "filtered".