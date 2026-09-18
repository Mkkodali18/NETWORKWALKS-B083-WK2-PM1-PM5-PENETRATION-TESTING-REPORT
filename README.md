# 🔎 NetworkWalks – Week 2

## Footprinting & Network Scanning

### 📌 Overview

This repository contains my **Week 2 practical work** completed as part of my **Cybersecurity & Ethical Hacking Internship at NetworkWalks**.

The focus of this week was **Footprinting, Information Gathering, Reconnaissance, and Network Scanning** using commonly used cybersecurity tools in an authorized testing environment.

The activities involved collecting publicly available information, analyzing DNS and HTTP information, identifying technologies, discovering hosts, and analyzing exposed ports and services.

---

## 🎯 Objectives

The main objectives of this practical exercise were to:

* Understand the fundamentals of footprinting and reconnaissance.
* Gather information about a target domain.
* Analyze DNS and domain-related information.
* Identify web technologies and security mechanisms.
* Inspect HTTP response headers.
* Perform host discovery.
* Identify open ports and running services.
* Analyze network scan results.
* Understand how reconnaissance supports penetration testing.
* Document technical observations and findings professionally.

---

## 🛠️ Tools Used

| Tool       | Purpose                                       |
| ---------- | --------------------------------------------- |
| WHOIS      | Domain registration and ownership information |
| nslookup   | DNS queries and resolution analysis           |
| wafw00f    | Web Application Firewall detection            |
| dnsrecon   | DNS enumeration                               |
| curl       | HTTP header analysis                          |
| WhatWeb    | Web technology fingerprinting                 |
| Nmap       | Host and port scanning                        |
| Zenmap     | Graphical interface for Nmap scanning         |
| Kali Linux | Security testing environment                  |

---

# 🔬 Practical Activities

## 1. WHOIS Analysis

WHOIS was used to gather domain-related information.

### Purpose

* Understand domain registration information.
* Identify registrar-related details.
* Review domain status and registration metadata.
* Understand the type of information that may be available during reconnaissance.

### Command

```bash
whois <target-domain>
```

### Observation

The WHOIS output was reviewed to understand publicly available domain information and how it can contribute to the reconnaissance phase of a security assessment.

---

## 2. nslookup Analysis

`nslookup` was used to perform DNS queries against the target.

### Purpose

* Resolve domain names to IP addresses.
* Identify DNS records.
* Understand the relationship between domains and IP addresses.

### Command

```bash
nslookup <target-domain>
```

### Observation

The DNS response was analyzed to understand the target's DNS resolution and associated infrastructure information.

---

## 3. WAF Detection with wafw00f

`wafw00f` was used to check whether a Web Application Firewall could be identified.

### Purpose

* Determine whether a WAF is present.
* Understand the security technologies protecting a web application.
* Identify information that may influence later security testing.

### Command

```bash
wafw00f <target-url>
```

### Observation

The tool output was analyzed to determine whether a recognizable Web Application Firewall was detected.

---

## 4. DNS Enumeration with dnsrecon

`dnsrecon` was used to perform DNS reconnaissance.

### Purpose

* Enumerate DNS information.
* Identify available DNS records.
* Understand the target's DNS infrastructure.

### Command

```bash
dnsrecon -d <target-domain>
```

### Observation

The DNS enumeration results were reviewed to identify relevant records and better understand the target's externally visible DNS configuration.

---

## 5. HTTP Header Analysis with curl

`curl` was used to inspect HTTP response headers.

### Purpose

* Examine HTTP responses.
* Identify server-related information.
* Review security-related HTTP headers.
* Understand how a web server responds to requests.

### Command

```bash
curl -I <target-url>
```

### Observation

The HTTP response headers were analyzed for server information and security-related configuration.

An exposed header or server information was treated as an **observation**, not automatically as a vulnerability.

---

## 6. Web Technology Fingerprinting with WhatWeb

WhatWeb was used to identify technologies associated with the target website.

### Purpose

* Identify web technologies.
* Detect frameworks and server technologies where possible.
* Understand the technology stack exposed by the application.

### Command

```bash
whatweb <target-url>
```

### Observation

The results were reviewed to understand the technologies and components visible from the external perspective.

---

# 🌐 7. Network Discovery with Nmap

Nmap was used to perform network discovery and identify available hosts and services.

### Purpose

* Discover active hosts.
* Identify open ports.
* Determine running services.
* Gather service/version information where available.

### Example Commands

```bash
nmap <target-ip>
```

```bash
nmap -sV <target-ip>
```

```bash
nmap -A <target-ip>
```

> Commands were used only within the authorized scope of the practical exercise.

---

# 🖥️ 8. Zenmap Scanning

Zenmap was used as the graphical interface for Nmap-based scanning.

### Purpose

* Perform network scans through a graphical interface.
* Review discovered hosts and ports.
* Analyze scan results visually.
* Understand Nmap profiles and output.

### Analysis

The Zenmap results were reviewed to identify:

* Discovered hosts
* Open ports
* Detected services
* Service versions where available
* Network-level observations

---

# 🔓 Port & Service Analysis

The discovered ports and services were reviewed as part of the reconnaissance process.

An **open port indicates that a service is reachable/listening**. It does not, by itself, prove that the service is vulnerable.

The assessment therefore focused on understanding:

```text
Open Port
    ↓
Associated Service
    ↓
Service Information
    ↓
Potential Exposure
    ↓
Further Security Assessment
```

This approach helps avoid incorrectly classifying normal service exposure as a confirmed vulnerability.

---

# 🗺️ Network Topology

The reconnaissance and scanning activities helped establish a basic understanding of the target's externally visible network structure.

```text
                Target Environment
                       │
                       ▼
                Domain / Website
                       │
          ┌────────────┴────────────┐
          ▼                         ▼
       DNS Info                 Web Server
          │                         │
          ▼                         ▼
    IP Resolution             HTTP/HTTPS
                                    │
                                    ▼
                             Open Services
                                    │
                                    ▼
                              Nmap / Zenmap
```

---

# 📊 Findings & Security Interpretation

The collected information was categorized into observations rather than automatically treating every result as a vulnerability.

### Key observations included:

* Domain and DNS information was identified.
* DNS records were analyzed.
* Web application protection mechanisms were checked.
* HTTP response headers were inspected.
* Web technologies were fingerprinted.
* Hosts and network services were identified through scanning.
* Open ports and associated services were analyzed.
* Reconnaissance information was used to understand the externally visible attack surface.

### Important Security Principle

> **Discovery is not the same as exploitation.**

An open port, detected technology, HTTP header, or DNS record may provide useful information during reconnaissance, but additional validation is required before classifying something as a security vulnerability.

---

# 🔄 Methodology

The practical exercise followed a structured reconnaissance workflow:

```text
Target Identification
        ↓
WHOIS Information Gathering
        ↓
DNS Enumeration
        ↓
Web Reconnaissance
        ↓
WAF Detection
        ↓
HTTP Header Analysis
        ↓
Technology Fingerprinting
        ↓
Host Discovery
        ↓
Port Scanning
        ↓
Service Identification
        ↓
Result Analysis
        ↓
Documentation
```

---

# 📸 Evidence

The repository/report includes screenshots documenting the practical activities and tool outputs.

The evidence covers activities such as:

1. WHOIS analysis
2. nslookup results
3. wafw00f results
4. dnsrecon results
5. curl HTTP headers
6. WhatWeb fingerprinting
7. Nmap scanning
8. Zenmap host discovery
9. Zenmap port/service results
10. Additional reconnaissance evidence

Screenshots are included to demonstrate the practical execution of the exercises and the corresponding observations.

---

# 📚 Learning Outcomes

Through this practical exercise, I developed hands-on understanding of:

* Footprinting
* Reconnaissance
* DNS enumeration
* WHOIS analysis
* Web reconnaissance
* WAF detection
* HTTP header analysis
* Web technology fingerprinting
* Network discovery
* Port scanning
* Service enumeration
* Nmap
* Zenmap
* Security assessment methodology
* Technical documentation

---

# ⚠️ Limitations

The activities documented in this repository represent reconnaissance and scanning exercises performed within an authorized learning environment.

The results should not be interpreted as a complete security assessment or proof of exploitable vulnerabilities.

Further validation, vulnerability analysis, and controlled testing would be required to confirm individual security findings.

---

# 🔐 Ethical & Legal Considerations

All activities documented in this repository were performed for **educational and authorized cybersecurity purposes**.

Security tools such as Nmap, WhatWeb, dnsrecon, and wafw00f can generate significant network traffic and should only be used against systems for which appropriate authorization has been obtained.

No unauthorized access, exploitation, or malicious activity is intended.

---

# 🚀 Internship Progress

**Program:** Cybersecurity & Ethical Hacking Internship
**Organization:** NetworkWalks
**Week:** 2
**Focus:** Footprinting, Reconnaissance & Network Scanning
**Status:** Ongoing

This week strengthened my understanding of how security professionals collect information about a target and analyze its externally visible attack surface before moving into deeper security testing.

---

## 👨‍💻 Author

**Kodali Mohana Krishna**

Aspiring Cybersecurity Professional

### Areas of Interest

* Cybersecurity
* Ethical Hacking
* Penetration Testing
* Vulnerability Assessment
* Network Security
* Security Operations
* Cloud Security

---

## ⭐ Repository Purpose

This repository is maintained as part of my cybersecurity learning journey and internship documentation.

It demonstrates my practical exposure to **reconnaissance, footprinting, network scanning, security tools, analysis, and professional security documentation**.

More practical exercises and projects will be added as the internship progresses.
