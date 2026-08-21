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
| Windows CMD |  To locate local IP      |
| Zenmap |   Graphical Nmap interface for network discovery     |
| Nmap |   Host discovery and network scanning    |

---

## 1️⃣ Footprinting usinf Multiple Kali Linux Tools

1. **WHOIS**: The command returned publicly available registration and domain infrastructure information, including details relating to the domain's registration and nameserver configuration. WHOIS information can assist an attacker during the reconnaissance phase by providing information about domain infrastructure and associated administrative or technical details.
   _COMMAND_: **whois networkwalks**
<img width="761" height="582" alt="whois snapshot" src="https://github.com/user-attachments/assets/f7ecfb85-5d02-44a5-8634-594c414b541c" />

2. **whatweb** : The scan identified web technologies associated with the website. It showed that the networkwalks webpage moved from http to https and it is currently on the Apache server, country is the United states, general information about the technology used.
   _COMMAND_: **whatweb networkwalks.com**
<img width="717" height="582" alt="whatweb result" src="https://github.com/user-attachments/assets/5ffd6011-cf6c-4aee-b318-60bea133ab07" />

3. **nslookup**: This tool was used to locate the domain name, server address and the IP address associated with the target. Identifying the IP address associated with a domain provides information about the infrastructure hosting the service.
   _COMMAND_: **nslookup networkwalks.com**
<img width="705" height="576" alt="nslookup result" src="https://github.com/user-attachments/assets/c6be6ecb-6b7f-4f26-a183-92be81bcbfac" />

4. **Curl**: Was used to identify the HTTP response header returned by the target.
   _COMMAND_: **curl -I https://networkwalks.com**
<img width="725" height="632" alt="curl result" src="https://github.com/user-attachments/assets/9956507c-30e7-4348-93d5-6aff2f81d839" />

5. **wafw00f**: This tool is used to see if the target is protected by any form of firewall and what type of firewall that would be. Identifying a WAF provides information about the defensive architecture of a web application. Although the presence of a WAF is generally a positive security control, revealing its technology can help an attacker understand the environment.
   _COMMAND_: **wafw00f https://networkwalks.com**
<img width="744" height="619" alt="wafw00f result" src="https://github.com/user-attachments/assets/2d28d202-4c5a-4b12-90e9-2b437b95828b" />

6. **DNSRecon**: This tool provides publicly available information on the DNS records. DNS information can help construct an infrastructure profile. For example, mail records can identify email infrastructure while TXT records may reveal configuration information or third-party services. DNS records should therefore be reviewed regularly to ensure that unnecessary information is not exposed.
   _COMMAND_: **dnsrecon -d networkwalks.com**
<img width="814" height="610" alt="dnsrecon" src="https://github.com/user-attachments/assets/fe40f383-6b72-4463-93cc-a3e39a2e437e" />

---

## 2️⃣ Network Scanning with Zenmap

Task 1: Download & install Zenmap from official website on your Windows PC

<img width="495" height="391" alt="nmap download" src="https://github.com/user-attachments/assets/8a67c02f-ae08-4a58-ac3d-661225cc3936" />

Task 2: Find your local IP address & your LAN subnet

<img width="641" height="205" alt="image" src="https://github.com/user-attachments/assets/33346d18-2d4c-4115-867b-8afc15bc49e6" />

Task 3: Find the list of live hosts/PC’s in your IP subnet

Task 4: How many hosts are live in your subnet? _3 HOSTS INCLUDING PC_

Task 5: What are the IP addresses of the live hosts?

Task 6: What are the MAC addresses of the live hosts?

Task 7: Display & save the output topology in PDF Format on your desktop

<img width="534" height="392" alt="image" src="https://github.com/user-attachments/assets/4566da45-80de-4423-8feb-4dce34173cb8" />


I used Zenmap to perform network discovery on my local network. The practical required me to identify my local IP address and subnet, discover live hosts, identify their IP and MAC addresses, and generate a network topology.
I first used the Windows ipconfig command to identify my local IP address and LAN subnet. I then
entered the subnet into Zenmap and selected Ping Scan to identify active hosts.

---

## Findings & Risk Analysis

The following findings represent observations made during the reconnaissance and network discovery exercises.
They should not be interpreted as confirmed vulnerabilities unless additional testing validates a security weakness.

| ✅ Finding                        | 🧾 Evidence                      | 🎯 Potential Impact              |
| ----------------------------- | ------------------------------- | ------------------------------- |
| Web technology information exposed          | WhatWeb                      | May assist attackers in identifying technologies requiring further security review       |
| Public server IP identifiable               | Nslookup                | Provides information about hosting/network infrastructure              |
| HTTP technical information exposed | Curl                  | May assist application and technology fingerprinting             |
| WAF technology identifiable        | Wafw00f     | Reveals information about defensive architecture                 |
| DNS infrastructure information exposed                | DNSRecon                | Can assist broader infrastructure reconnaissance        |
| Multiple live hosts identified            | Zenmap | Unexpected devices may increase the attack surface |

---

## 📝 Recommendation 

Based on the observations made during the lab, the following security improvements are recommended:

1. Minimize unnecessary information exposure

Review publicly accessible web server, CMS, plugin, and HTTP information and remove unnecessary technical details where practical.

2. Maintain software securely

Keep WordPress, plugins, web servers, operating systems, and other exposed technologies updated according to the organization's patch-management process.

3. Review HTTP security configuration

Regularly review HTTP response headers and web server configuration to identify unnecessary information disclosure.

4. Review public DNS records

Perform periodic DNS reviews to ensure that obsolete, unnecessary, or unintended records are removed.

5. Maintain WAF protection

Keep the WAF enabled and properly configured. Monitor WAF events and periodically review its effectiveness.

6. Maintain an internal asset inventory

Organizations should maintain an up-to-date list of authorized network devices.

7. Investigate unknown hosts

Unexpected devices discovered during internal network scans should be identified and verified.

8. Segment critical systems

Where appropriate, sensitive systems should be isolated using network segmentation and access controls.

9. Perform periodic authorized assessments: Reconnaissance, network discovery, vulnerability assessment, and penetration testing should be performed periodically within a clearly defined and authorized scope.

---

## 🔚 Conclusion 

The Week 2 practical provided hands-on experience with two fundamental areas of penetration testing: reconnaissance and network discovery.

During the reconnaissance phase, WHOIS, WhatWeb, Nslookup, Curl, Wafw00f, and DNSRecon were used to collect information about the authorized domain. The exercise demonstrated how information such as domain infrastructure, DNS records, web technologies, HTTP headers, and WAF technologies can contribute to an attacker's understanding of a target.

During the internal network discovery phase, Windows networking commands and Zenmap were used to identify the local network configuration and discover active hosts. The results were then used to create a basic network topology.

An important lesson from the exercise was that information gathered during reconnaissance is not automatically a vulnerability. Technology versions, IP addresses, DNS records, and discovered hosts are observations that may become security concerns depending on how the underlying systems are configured.

The exercise also demonstrated the importance of documenting security testing clearly. A professional penetration-testing report should explain the scope, methodology, evidence, observations, potential impact, risk level, recommendations, and limitations.

Overall, the lab provided practical experience with the reconnaissance stage of a penetration test and demonstrated why careful information gathering is an important step before vulnerability validation and exploitation.
---
