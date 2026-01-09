Firewall Validation Analysis

Nmap SYN scans from Kali Linux reported all ports as **filtered**.


Interpretation
Filtered ports indicate:
- Packets reached the host
- No response was returned
- Firewall silently dropped probes

Supporting Evidence
- tcpdump confirmed incoming SYN packets
- No SYN-ACK responses observed
- Firewall logs recorded dropped traffic

Conclusion
Firewall behavior aligns with stealth hardening objectives.