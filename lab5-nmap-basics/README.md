# Lab 05 – Nmap Basics

## Objective

The objective of this lab was to learn the fundamentals of Nmap (Network Mapper), a powerful network scanning tool used to discover hosts, identify open ports, detect running services, and gather information about systems on a network. Understanding Nmap is essential for security professionals performing network assessments and investigations.

---

## Environment

- **Operating System:** Kali Linux
- **Shell:** Bash
- **Virtualization:** VirtualBox
- **Tool:** Nmap

---

## Learning Objectives

By completing this lab, I aimed to:

- Understand the purpose of Nmap.
- Perform basic network scans.
- Identify open TCP ports.
- Detect running services and versions.
- Perform operating system detection.
- Save scan results for documentation and analysis.
- Understand how Nmap supports security operations.

---

## Background Theory

Nmap (Network Mapper) is an open-source network discovery and security auditing tool. It is widely used by network administrators and cybersecurity professionals to discover devices on a network, identify open ports, detect running services, and perform security assessments.

Every network service listens on a specific port. Identifying which ports are open helps determine which services are available and whether unnecessary or insecure services are exposed.

> **Important:** Nmap should only be used on systems you own or have explicit permission to scan.

---

## Commands Practiced

| Command | Purpose |
|---------|---------|
| `nmap --version` | Display the installed Nmap version |
| `nmap localhost` | Scan the local machine for open ports |
| `ip addr` | Display the system's IP address |
| `nmap <your-ip-address>` | Scan the local system using its IP address |
| `nmap -p 22 localhost` | Scan a specific port |
| `nmap -p 22,80,443 localhost` | Scan multiple specified ports |
| `sudo nmap -sV localhost` | Detect service versions |
| `sudo nmap -O localhost` | Attempt operating system detection |
| `sudo nmap -A localhost` | Perform an aggressive scan (OS, version, scripts, traceroute) |
| `nmap localhost -oN scan-results.txt` | Save scan results to a text file |

---

## Screenshots

### Nmap Version

![version](screenshots/version.png)

---

### Scan Localhost

![localhost](screenshots/localhost.png)

---

### Scan Local IP Address

![ip scan](screenshots/ip-scan.png)

---

### Scan a Specific Port

![port22](screenshots/port22.png)

---

### Scan Multiple Ports

![multiple ports](screenshots/multiple-ports.png)

---

### Service Version Detection

![service detection](screenshots/service-detection.png)

---

### Operating System Detection

![os detection](screenshots/os-detection.png)

---

### Aggressive Scan

![aggressive scan](screenshots/aggressive-scan.png)

---

### Saved Scan Results

![scan results](screenshots/scan-results.png)

---

## Observations

- Nmap successfully identified open ports on the target system.
- The scan displayed the state of each port (open, closed, or filtered).
- Service version detection revealed the applications listening on open ports.
- Operating system detection attempted to identify the host operating system.
- Aggressive scanning provided additional information such as scripts, services, and routing details.
- Scan results were successfully exported for future reference.

---

## What I Learned

- How to perform basic host discovery.
- How to identify open ports.
- How to detect running services.
- The difference between scanning localhost and scanning an IP address.
- How to save scan results for documentation.
- Why understanding exposed services is important for security.

---

## Challenges Faced

Some advanced scan types, such as operating system detection (`-O`) and aggressive scans (`-A`), may require administrative privileges and may not always produce accurate results in a virtual machine environment. Running the commands with `sudo` and understanding the limitations of virtualized environments helped complete the lab.

---

## SOC Relevance

Nmap is a valuable tool for Security Operations Center (SOC) Analysts because it helps to:

- Discover devices on a network.
- Identify unexpected or unauthorized services.
- Verify exposed ports during investigations.
- Support vulnerability assessments.
- Validate asset inventories.
- Assist with incident response and network troubleshooting.

Understanding Nmap output allows analysts to better assess the security posture of systems and identify potential attack surfaces.

---

## Key Takeaways

- Nmap is one of the most widely used network scanning tools.
- Open ports indicate services that may require monitoring or hardening.
- Service detection helps identify software running on target systems.
- Scan results should always be interpreted carefully and within an authorized environment.
- Documentation of scan findings is an important part of cybersecurity investigations.

---

## Outcome

Successfully performed multiple Nmap scans to identify hosts, open ports, running services, and operating system information while documenting the results as part of my SOC Analyst learning journey.
