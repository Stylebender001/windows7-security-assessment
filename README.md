# Windows 7 Security Assessment

## Project Overview

A network reconnaissance, service enumeration, and vulnerability assessment conducted against a Windows 7 Professional SP1 virtual machine using Kali Linux.

The assessment focused on identifying exposed network services, enumerating SMB configurations, detecting known vulnerabilities, and researching publicly available exploits.

## Assessment Environment

| Component | Details |
|---|---|
| Target | Windows 7 Professional SP1 |
| Target IP | 192.168.1.99 |
| Operating System Build | 7601 |
| Architecture | x64 |
| Attacker Machine | Kali Linux |
| Virtualization | Oracle VirtualBox |
| Assessment Date | 17 October 2026 |

## Tools Used

- **Nmap** – Host discovery, port scanning, service detection, OS fingerprinting, and vulnerability scanning.
- **SearchSploit** – Public exploit research.
- **SMB Enumeration Tools** – Share discovery and access assessment.

## Key Findings

| Finding | Port / Service | Risk |
|---|---|---|
| MS17-010 vulnerability detected | TCP 445 / SMB | Critical |
| SMB service exposed | TCP 445 | High |
| NetBIOS service exposed | TCP 139 | Medium |
| Microsoft RPC services exposed | TCP 135 and dynamic RPC ports | Medium |
| Microsoft HTTPAPI service exposed | TCP 5357 | Informational |

**Major Finding:** Nmap's SMB vulnerability script reported the target as vulnerable to MS17-010, which covers multiple SMBv1 vulnerabilities, including EternalBlue (CVE-2017-0144).

## Assessment Methodology

1. Host discovery and network identification.
2. TCP port scanning.
3. Service and version enumeration.
4. Operating system identification.
5. SMB share enumeration.
6. Automated vulnerability detection.
7. Public exploit research using SearchSploit.
8. Risk assessment and remediation recommendations.

## Exploit Research

SearchSploit was used to identify publicly documented exploit references associated with MS17-010.

Exploit research was conducted for educational purposes. No exploit execution or successful remote code execution was performed during this assessment.

## Recommendations

- Apply the appropriate MS17-010 security updates.
- Disable SMBv1 where it is not required.
- Restrict access to TCP port 445.
- Review SMB signing configuration.
- Restrict unnecessary NetBIOS and RPC exposure.
- Migrate from Windows 7 to a supported operating system.


## Disclaimer

This assessment was conducted against an intentionally configured Windows 7 virtual machine in an authorized laboratory environment.

The project documents reconnaissance, enumeration, vulnerability detection, and exploit research only. It does not represent a real-world client assessment or successful exploitation.

## Author

**Shardul Sapkota**

Cybersecurity | Network Security | Vulnerability Assessment
