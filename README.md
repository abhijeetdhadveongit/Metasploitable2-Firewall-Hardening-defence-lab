Metasploitable2 Firewall Hardening (Blue Team Project)

Overview
This project demonstrates how a *host-based firewall (iptables)* can be used to
significantly reduce the attack surface of a deliberately vulnerable system
(**Metasploitable2**).

Rather than attempting to patch vulnerabilities, the project focuses on
*defensive controls*, *stealth firewall behavior*, and *attack surface reduction*.

---

## Objectives
- Analyze exposed services on Metasploitable2
- Design a default-deny firewall policy
- Implement iptables-based controls
- Validate firewall effectiveness using Nmap and tcpdump
- Document defensive security outcomes

---

## Lab Environment
Component details 

Attacker - Kali Linux 2025 
Target - Metasploitable2 (Ubuntu 8.04, Kernel 2.6) 
Hypervisor - VMware Workstation 
Network - Host-Only 

---

## Key Result
After firewall deployment:

- Host remains reachable
- All TCP ports appear **filtered**
- No services are remotely enumeratable
- Packet drops are silent (stealth mode)

This behavior confirms **successful firewall hardening**, not misconfiguration.

---

## Before vs After

Before - 
1.Open ports - 25 +.
2.Port scan visibility - high.
3.Attack surface - Extremely high.
4.Recon effectiveness - Full.

After - 
1.Open ports - 0.
2.Port scan visibility - None.
3.Attack surface - Minimal.
4.Recon effectiveness - Ineffective.
---

## Project Structure
See repository folders for:
- Firewall rules
- Scan outputs
- Validation evidence
- Final security report

---

## Skills Demonstrated
- Linux firewall administration
- Network traffic analysis
- Nmap interpretation
- Blue team defensive thinking
- Legacy system hardening

---

## Disclaimer
This project is for **educational purposes only**, conducted in an isolated lab.
Metasploitable2 should never be exposed to production networks.

---

## 👤 Author
Abhijeet Dhadve
Cybersecurity / Blue Team / SOC Analyst (Aspirant)