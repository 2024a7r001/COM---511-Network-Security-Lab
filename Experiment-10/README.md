

# EXPERIMENT 10: Setup and Test a Simple Intrusion Detection System (IDS) with Snort

## Aim / Objective
To install, configure and test Snort IDS on pfSense, simulate network attacks and analyze suspicious network traffic through generated alerts.

## Requirements
- pfSense 2.9.0 Virtual Machine
- Kali Linux Virtual Machine
- Snort Package
- VMware Virtualization Environment
- Nmap and Ping Utilities
- Network Connectivity between Virtual Machines

## Methodology / Procedure
1. Start pfSense and configure WAN and LAN interfaces with the LAN IP `192.168.122.1/24`.
2. Identify the Kali Linux IP address using the `ifconfig` command.
3. Configure firewall rules under Firewall → Rules → LAN.
4. Navigate to Services → Snort → Interfaces and configure Snort on the LAN (em1) interface.
5. Verify that Snort is running with AC-BNFA pattern matching.
6. Generate ICMP traffic using `ping 192.168.122.129 -c 4`.
7. Perform a port scan using `nmap -p 1-1000 192.168.122.129`.
8. Navigate to Services → Snort → Alerts and analyze the generated alerts.

## Context / Theory
An Intrusion Detection System (IDS) monitors network traffic to identify suspicious activities and potential attacks. Snort is an open-source network intrusion detection tool that analyzes packets using predefined rules and generates alerts when suspicious traffic patterns are detected.

In this experiment, pfSense acts as the firewall and IDS platform, Kali Linux generates test traffic, and Snort monitors network activities and records alerts.

## Visualization

```text
       KALI LINUX
   (192.168.122.128)
           |
           | Nmap Scan / Ping
           v
      +-----------+
      |  pfSense  |
      | Firewall  |
      +-----------+
           |
           v
      +-----------+
      | Snort IDS |
      | Monitoring|
      +-----------+
           |
           v
      +-----------+
      | Traffic   |
      | Analysis  |
      +-----------+
           |
           v
      +-----------+
      | Alert Logs|
      | Detection |
      +-----------+
```

## Results
Snort IDS was successfully configured and activated on the pfSense LAN interface. Network connectivity was verified, and Nmap identified 12 open TCP ports on the target system. Snort generated ICMP Ping Detected alerts during traffic monitoring. The experiment demonstrated successful intrusion detection and network traffic analysis. Configuration steps, commands, screenshots and output analysis are documented in this GitHub repository.

## Discussion
The experiment demonstrated how Snort monitors network traffic and detects suspicious activities. Nmap scanning helped identify open ports and running services on the target machine. Snort alert logs displayed ICMP-related detection events. pfSense firewall rules helped control network traffic. Overall, the experiment provided practical understanding of intrusion detection and network security monitoring.

## Improvements
- Regularly update Snort detection rules and signatures.
- Enable blocking mode after validating detection rules.
- Add custom rules to detect port scanning activities.
- Monitor and analyze alert logs regularly.
- Restrict unnecessary open ports using firewall rules.
- Test the IDS with different types of controlled network traffic.

## Conclusion
Snort IDS was successfully configured and tested using pfSense. Network scanning, ICMP testing and alert monitoring demonstrated how suspicious network activities can be detected and analyzed.
