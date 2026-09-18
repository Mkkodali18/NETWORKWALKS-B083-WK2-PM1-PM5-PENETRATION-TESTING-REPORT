# cybersecurity-Week-2
FOOTPRINTING & NETWORK SCANNING

Professional Cybersecurity Practical Report

Project Area

Cybersecurity / Ethical Hacking

Primary Activities

Domain Footprinting, Web Fingerprinting, DNS Enumeration, Network Scanning

Primary Tools

WHOIS, nslookup, WhatWeb, wafw00f, dnsrecon, curl, Nmap / Zenmap

Reference Repository

pritesh460/Cybersecurity_internship — Footprinting & Network Scanning

Evidence

Terminal and Zenmap screenshots supplied with the project

Report Date

18 September 2026

This report documents reconnaissance and network-scanning observations from the supplied evidence. Open ports, technology fingerprints, and DNS records are observations—not proof of a vulnerability. Active testing must be limited to authorized systems.

1. Executive Summary

This practical exercise demonstrates a structured cybersecurity reconnaissance workflow covering domain footprinting and network scanning. The domain phase used WHOIS, nslookup, WhatWeb, wafw00f, dnsrecon and curl to identify registration, DNS, hosting, web-server, application and WAF characteristics associated with networkwalks.com.

The network-scanning phase used Nmap/Zenmap to discover live hosts and enumerate exposed or filtered TCP services in the supplied lab/network evidence.

2. Objectives

Understand footprinting and reconnaissance methodology.

Collect domain-registration and DNS information.

Identify web technologies and server characteristics.

Detect WAF indicators from external responses.

Use Nmap/Zenmap for authorized host and port discovery.

Interpret scan results conservatively and document evidence professionally.

3. Scope, Authorization & Ethics

The report is based on the supplied screenshots and the referenced Footprinting & Network Scanning repository. The evidence includes the public target networkwalks.com and private/lab addresses used for Zenmap practice.

Scanning should only be performed against systems owned by the tester or explicitly authorized for assessment. Before publishing screenshots, redact private IPs, MAC addresses, usernames, cookies and tokens.

4. Tools & Technologies

WHOIS — registration and registrar information.

nslookup — DNS resolution.

WhatWeb — web technology fingerprinting.

wafw00f — WAF detection.

dnsrecon — DNS record enumeration.

curl -I — HTTP header inspection.

Nmap/Zenmap — host discovery, port scanning and topology visualization.

5. Part A — Domain Footprinting

WHOIS evidence: GoDaddy.com, LLC registrar; creation 2019-11-06; updated 2025-11-12; expiry 2027-11-06; HostGator name servers NS6135.HOSTGATOR.COM and NS6136.HOSTGATOR.COM; DNSSEC unsigned.

nslookup evidence: DNS server 8.8.8.8; networkwalks.com resolved to 192.232.216.135.

wafw00f evidence: ModSecurity (SpiderLabs) detected.

dnsrecon evidence: SOA, NS, A, TXT and SRV records, including autodiscover/cPanel-related mail infrastructure.

curl -I evidence: HTTP/2 200 with Apache, WordPress-related and security/policy headers.

WhatWeb evidence: WordPress, Apache, Bootstrap, jQuery, Google Tag Manager and related fingerprints.

6. Part B — Network Scanning

Zenmap ping-scan evidence used nmap -sn 10.0.0.2/24 and displayed live hosts including 10.0.0.1 and 10.0.0.2.

A separate lab view showed localhost/127.0.0.1 and private addresses including 172.20.10.7 and 192.168.56.1.

The supplied Zenmap result for 192.168.56.1 reported 135/tcp msrpc, 445/tcp microsoft-ds and 5357/tcp wsdapi as open.

The networkwalks.com quick scan reported: 21/ftp open, 22/ssh open, 25/smtp filtered, 26/rsftp open, 53/domain open, 80/http open, 110/pop3 open, 135/msrpc filtered, 139/netbios-ssn filtered, 143/imap open, 443/https open, 445/microsoft-ds filtered, 465/smtps open, 587/submission open, 993/imaps open, 995/pop3s open and 3306/mysql open.

Open or filtered ports do not by themselves establish exploitable vulnerabilities; service versions, configuration, authentication and exposure context must be validated.

7. Findings & Security Interpretation

Domain registration and DNS records provide infrastructure intelligence.

Web technology fingerprints can help maintain patch and asset inventories.

WAF detection indicates an application-layer filtering control, but effectiveness requires authorized validation.

Internet-facing services should be justified, patched, monitored and restricted to required sources.

Database and management services should be segmented and protected from unnecessary internet exposure.

8. Workflow / Methodology

Scope → passive footprinting → DNS enumeration → technology discovery → host discovery → port scanning → interpretation → evidence collection → professional reporting.

9. Learning Outcomes

Practical use of Linux reconnaissance tools and Nmap/Zenmap.

Understanding open versus filtered ports.

Reading WHOIS, DNS, HTTP-header, WAF and technology-fingerprint output.

Applying ethical boundaries and evidence-driven reporting.

10. Limitations

The report reflects the supplied screenshots and may not represent the target's current state.

Quick scans are limited and do not identify every service or vulnerability.

Technology fingerprints can be imperfect.

No authenticated testing, exploitation, source-code review or remediation verification is documented.

11. Conclusion

The exercise demonstrates a complete reconnaissance-to-scanning workflow. Footprinting built a technical profile of networkwalks.com, while Zenmap demonstrated host discovery, topology visualization and service enumeration. The defensive value comes from turning these observations into an accurate asset inventory, reducing unnecessary exposure, hardening required services and monitoring changes over time.

12. Ethical & Professional Statement

All active scanning should be conducted only within an explicitly authorized scope. The work is intended for cybersecurity education and defensive assessment.

13. Evidence Appendix — Supplied Screenshots

SUBMISSION NOTE: Replace any supplied/example evidence below with your own Week 2 screenshots where required.



Evidence 1 — WHOIS domain registration output for networkwalks.com.



Evidence 2 — nslookup DNS resolution output.



Evidence 3 — wafw00f WAF detection output.



Evidence 4 — dnsrecon DNS enumeration output.



Evidence 5 — curl HTTP header inspection output.



Evidence 6 — Zenmap host discovery/topology view for the lab subnet.



Evidence 7 — WhatWeb technology fingerprinting output.



Evidence 8 — Zenmap local/lab topology view.



Evidence 9 — Zenmap quick-scan results showing open/filtered services.



Evidence 10 — Additional Zenmap scan evidence for the target domain.

