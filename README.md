# networkwalks-B082-week2
This project contains two stages of cybersecurity: Reconnaissance (Footprinting) and Scanning a Target Network 


<div align="center">

# 🔐 PENETRATION TESTING REPORT: FOOTPRINTING &amp; NETWORK SCANNING PHASES (networkwalks.com)

**Testing different Kali Linux tools as an Authorized Tester, Using windows to locate webcams, Footprinting with Maltego...and more**
</div>

<p align="center">
  <img src="https://img.shields.io/badge/Skill-Cybersecurity-404040?style=flat-square&labelColor=C0000" />
  <img src="https://img.shields.io/badge/Ver-Virtualbox%20v7.2-0070C0?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Kali%20Linux-v2026.2-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Skill-Linux-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Penetration%20Testing-C00000?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Skill-Virtualization-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/GitHub-404040?style=flat-square&labelColor=0070C0&logo=github&logoColor=white" />
  <img src="https://img.shields.io/badge/Kali%20Linux-404040?style=flat-square&labelColor=C00000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/NetworkWalks-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Ethical%20Hacking-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Ibunkunoluwa%20Fasesan-E0FFFF?style=flat-square" />
</p>

---

|  Pentester Name       | Ibunkunoluwa Fasesan   |
| ------------------ | ------------------  |
|  Program/Batch         | B082-Networkwalks        |
|  Date       | 20th August 2026               |
| Modules completed       | W2-PM1 (Multiple Kali Tools); W2-PM5 (Zenmap Scanning)    |
| Client/Target      | 1. Networkwalks (secured written permission already), 2. My own local LAN Network  |
| Permission secured from client?     | Yes  |
| Phases covered       | Phase 1: Reconnaissance &amp; Footprinting          |
|  | Phase 2: Scanning &amp; Network Discovery        |
|  | Phase 3-5: In Progress       |

---

## 🔔 Liability Disclaimer

I have performed these activities only on the systems &amp; devices where I had secured written permission
or the devices/systems that I own myself. All these materials are for education and research purpose
only. Do not use anything from here to break the law. Every action you take is your own responsibility.
Misuse can lead to criminal charges, heavy fines, loss of your job and a permanent record. In most
countries unauthorized access is a crime even when nothing is damaged.

---

## 🔰 Introduction/ Project Summary

This report contains reconnaissance (footprinting) and network discovery activities completed in the 2nd week of the internship program with Networkwalks. This lab had two primary activities:
1. Web and domain reconnaissance against the assigned networkwalks.com domain using Kali Linux tools.
2. Internal network discovery against an authorized local network using Zenmap/Nmap.
The first activity focused on studying the structure of the target, identifying the public information of the target and the type of firewall protecting the target....and so more.
The second activity

The assessment demonstrates how an attacker could begin building an understanding of an environment before attempting further security testing. The findings identified several areas that could provide useful reconnaissance information to an attacker, although these observations do not independently confirm the presence of exploitable vulnerabilities.
---

## 🎯 Lab Objectives

The main objectives of this project are to:

- Understand the footprinting phase of a penetration test.
- Identify publicly available information associated with a domain.
- Determine the technologies and services exposed by a web application.
- Identify whether a Web Application Firewall is present.
- Understand the importance of performing reconnaissance and scanning only within an authorized scope.

---

## ⚙️ Tools and Technologies

The lab provides an isolated and controlled environment for cybersecurity learning and authorized security testing.

|  Tool       | Purpose |
| ------------------ | ------------------  |
|  Kali Linux        | This was the footprinting test environment       |
| WHOIS      | Provided all the publicly available information like the domain name, registrar URL, creation date etc               |
| whatweb      | Fingerprint web technologies (server, CMS, plugins, IP).    |
| nslookup     | Used for DNS and IP identification  |
| curl     | HTTP header information  |
| wafw00f       | Used to detect and identify the firewall used in a server          |
| dnsrecon | All DNS records        |
| Windows CMD |        |
| Zenmap |        |
| Nmap |       |

---

## 1️⃣ Footprinting usinf Multiple Kali Linux Tools

1. **WHOIS**: The command returned publicly available registration and domain infrastructure information, including details relating to the domain's registration and nameserver configuration. WHOIS information can assist an attacker during the reconnaissance phase by providing information about domain infrastructure and associated administrative or technical details.
COMMAND: whois networkwalks
<img width="761" height="582" alt="whois snapshot" src="https://github.com/user-attachments/assets/f7ecfb85-5d02-44a5-8634-594c414b541c" />

2.** whatweb**: The scan identified web technologies associated with the website. It showed that the networkwalks webpage moved from http to https and it is currently on the Apache server, country is the United states, general information about the technology used.
COMMAND: whatweb networkwalks.com
<img width="717" height="582" alt="whatweb result" src="https://github.com/user-attachments/assets/5ffd6011-cf6c-4aee-b318-60bea133ab07" />

3. **nslookup**: This tool was used to locate the domain name, server address and the IP address associated with the target. Identifying the IP address associated with a domain provides information about the infrastructure hosting the service.
COMMAND: nslookup networkwalks.com
<img width="705" height="576" alt="nslookup result" src="https://github.com/user-attachments/assets/c6be6ecb-6b7f-4f26-a183-92be81bcbfac" />

4. **Curl**: Was used to identify the HTTP response header returned by the target.
COMMAND: curl -I https://networkwalks.com
<img width="725" height="632" alt="curl result" src="https://github.com/user-attachments/assets/9956507c-30e7-4348-93d5-6aff2f81d839" />

5. **wafw00f**: This tool is used to see if the target is protected by any form of firewall and what type of firewall that would be. Identifying a WAF provides information about the defensive architecture of a web application. Although the presence of a WAF is generally a positive security control, revealing its technology can help an attacker understand the environment.
COMMAND: wafw00f https://networkwalks.com
<img width="744" height="619" alt="wafw00f result" src="https://github.com/user-attachments/assets/2d28d202-4c5a-4b12-90e9-2b437b95828b" />

6. **DNSRecon**: This tool provides publicly available information on the DNS records. DNS information can help construct an infrastructure profile. For example, mail records can identify email infrastructure while TXT records may reveal configuration information or third-party services. DNS records should therefore be reviewed regularly to ensure that unnecessary information is not exposed.
COMMAND: dnsrecon -d networkwalks.com
<img width="814" height="610" alt="dnsrecon" src="https://github.com/user-attachments/assets/fe40f383-6b72-4463-93cc-a3e39a2e437e" />

---

## 2️⃣ Lab Objectives

The main objectives of this project are to:

- Understand the footprinting phase of a penetration test.
- Identify publicly available information associated with a domain.
- Determine the technologies and services exposed by a web application.
- Identify whether a Web Application Firewall is present.
- Understand the importance of performing reconnaissance and scanning only within an authorized scope.

---

---

## 🎯 Lab Objectives

The main objectives of this project are to:

- Understand the footprinting phase of a penetration test.
- Identify publicly available information associated with a domain.
- Determine the technologies and services exposed by a web application.
- Identify whether a Web Application Firewall is present.
- Understand the importance of performing reconnaissance and scanning only within an authorized scope.

---

---

## 🎯 Lab Objectives

The main objectives of this project are to:

- Understand the footprinting phase of a penetration test.
- Identify publicly available information associated with a domain.
- Determine the technologies and services exposed by a web application.
- Identify whether a Web Application Firewall is present.
- Understand the importance of performing reconnaissance and scanning only within an authorized scope.

---

---

## 🎯 Lab Objectives

The main objectives of this project are to:

- Understand the footprinting phase of a penetration test.
- Identify publicly available information associated with a domain.
- Determine the technologies and services exposed by a web application.
- Identify whether a Web Application Firewall is present.
- Understand the importance of performing reconnaissance and scanning only within an authorized scope.

---

---

## 🎯 Lab Objectives

The main objectives of this project are to:

- Understand the footprinting phase of a penetration test.
- Identify publicly available information associated with a domain.
- Determine the technologies and services exposed by a web application.
- Identify whether a Web Application Firewall is present.
- Understand the importance of performing reconnaissance and scanning only within an authorized scope.

---
