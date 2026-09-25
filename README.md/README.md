# Metasploitable 2 — Information Gathering & Reconnaissance Lab

A hands-on cybersecurity reconnaissance lab performed using **Kali Linux** against an intentionally vulnerable **Metasploitable 2** virtual machine.

The purpose of this project was to practice information gathering and reconnaissance techniques, identify the target and its attack surface, and document the findings obtained from different security tools.

---

##  Objectives

The main objectives of this lab were to:

* Verify connectivity with the target
* Discover active hosts on the lab network
* Identify open ports
* Enumerate running services and their versions
* Identify the probable operating system
* Practice DNS enumeration
* Identify web technologies
* Document reconnaissance findings
* Understand how reconnaissance information can support subsequent vulnerability assessment

---

## Lab Environment

| Component        | Details                               |
| ---------------- | ------------------------------------- |
| Attacker Machine | Kali Linux                            |
| Target Machine   | Metasploitable 2                      |
| Kali IP          | `192.168.200.130`                     |
| Target IP        | `192.168.200.131`                     |
| Network          | `192.168.200.0/24`                    |
| Environment      | Authorized cybersecurity practice lab |

---

## 🛠️ Tools Used

* **Ping** — Target connectivity verification
* **Nmap** — Host discovery, port scanning, service/version enumeration and OS detection
* **dig** — DNS record enumeration
* **nslookup** — DNS queries
* **WhatWeb** — Web technology identification
* **WHOIS** — Domain/registration information gathering
* **Subdomain enumeration tools** — Subdomain discovery

---

## 🔍 Reconnaissance Activities

### 1. Target Connectivity

The first step was to verify communication between Kali Linux and the Metasploitable 2 target.

```bash
ping -c 4 192.168.200.131
```

The target responded to the ICMP requests, confirming connectivity between the two virtual machines.

---

### 2. Host Discovery

Nmap was used to identify active hosts within the lab network.

```bash
nmap -sn 192.168.200.0/24
```

The scan identified active hosts on the local network, including the Metasploitable 2 target.

---

### 3. Port Scanning

Nmap was used to identify open TCP ports on the target.

```bash
nmap 192.168.200.131
```

The scan identified multiple open ports, indicating the presence of several network services.

> **Note:** The specific port results are documented in the reconnaissance report and screenshots.

---

### 4. Service and Version Enumeration

Nmap service/version detection was performed to identify applications and their versions.

```bash
nmap -sV 192.168.200.131
```

The results provided information about the services running on the discovered ports and their versions.

This information can be useful during subsequent vulnerability assessment because specific software versions may have known vulnerabilities.

---

### 5. Operating System Detection

Nmap OS detection was used to identify the probable operating system and kernel information of the target.

```bash
sudo nmap -O 192.168.200.131
```

---

### 6. DNS Enumeration

DNS enumeration was practiced to understand how DNS records can provide information about domains and their infrastructure.

The following record types were examined:

```text
A
AAAA
MX
NS
TXT
SOA
```

Commands included:

```bash
dig <authorized-domain> A
dig <authorized-domain> MX
dig <authorized-domain> NS
dig <authorized-domain> TXT
dig <authorized-domain> SOA
```

and:

```bash
nslookup <authorized-domain>
```

### DNS Record Types

| Record | Purpose                                              |
| ------ | ---------------------------------------------------- |
| A      | Maps a domain to an IPv4 address                     |
| AAAA   | Maps a domain to an IPv6 address                     |
| MX     | Identifies mail servers                              |
| NS     | Identifies authoritative name servers                |
| TXT    | Contains text-based information                      |
| SOA    | Provides administrative information about a DNS zone |

---

### 7. Web Technology Enumeration

WhatWeb was used to identify technologies associated with the web server running on the target.

```bash
whatweb http://192.168.200.131
```

The scan provided information about the web server, operating system and web technologies detected on the target.

---

##  Key Findings

The reconnaissance activities provided the following findings:

* The Metasploitable 2 target was reachable from Kali Linux.
* Multiple network ports were identified as open.
* Several running services and their versions could be identified.
* Nmap provided information about the probable operating system.
* Web technologies associated with the target's web server could be identified.
* DNS enumeration demonstrated how different DNS record types can provide infrastructure-related information.

---

##  Security Relevance

Reconnaissance is an important phase of security testing because information collected during this phase can help identify a target's attack surface.

The information gathered during this lab included:

* IP addresses
* Open ports
* Running services
* Software versions
* Operating system information
* DNS records
* Web technologies

This information can be used during subsequent vulnerability assessment and security testing.

---

##  What I Learned

Through this lab, I gained practical experience with reconnaissance and information gathering tools.

I learned how to:

* Perform host discovery
* Identify open ports
* Enumerate services and versions
* Perform OS detection
* Perform DNS enumeration
* Identify web technologies
* Correlate information obtained from multiple security tools
* Document reconnaissance findings in a structured report

---

##  Project Structure

```text
metasploitable2-information-gathering-lab/
│
├── README.md
├── final-recon-report.md


---

##  Full Reconnaissance Report

The detailed reconnaissance report contains the commands, observations, findings and screenshots from the lab.

**[View Full Reconnaissance Report](final-recon-report.md)**

---

##  Disclaimer

This project was performed in an isolated and authorized cybersecurity practice environment using Metasploitable 2, an intentionally vulnerable virtual machine.

The techniques demonstrated in this project should only be used against systems for which proper authorization has been obtained.
