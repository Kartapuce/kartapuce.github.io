---
layout: single
author_profile: false
title: "Detection and Response"
excerpt: "What's going on in my realm ?"
sidebar:
  nav: "architecture"
header:
  teaser: /assets/images/Detect and Respond-small.png
gallery1:
  - url: /assets/images/Detect and Respond.png
    image_path: assets/images/Detect and Respond.png
---

## Architecture

This model highlights some of the security tools involved in the detection and response process.

{% include gallery id="gallery1" type="center" %}

## Detection & Response tools

Marketing loves cybersecurity. :heart: Let's try to shed some light on the marketing buzzwords.

### Network tools

**NIDS (Network Intrusion Detection System)**: Signature-based detection of malicious network activity. It interfaces with the network with port-mirroring or a TAP.  
**NTA (Network Traffic Analysis) = NIDS++**: Enhance NIDS capacities with netflow capture, full packet capture, behavioral analytics (burst of activities...), passive vulnerability scanning, shadow IT detection...  
**NDR (Network Detection & Response) = NTA++**: Enhance NTA capacities with automatic remediation, and add playbooks for guidance.

### Endpoint tools

**Antivirus**: Signature-based detection of malware thanks to files analysis.  
**EPP (Endpoint Protection Platform) = Antivirus++**: Enhance 0-day detection based on known attack patterns and endpoint suspicious activities. It may add automatic remediation.  
  
**HIDS (Host Intrusion Detection System)**: Reinforce antivirus detection with bahavior-based detection and endpoint suspicious activities. Usually less resource consuming than antivirus as it does not analyse all the memory blocks.  
**EDR (Endpoint Detection & Response) = HIDS++**: Enhance HIDS detection with automatic remediation.

### Analysis tools

**SIEM (Security Information and Event Management)**: Centralization of security events, advanced analysis features (correlation, machine learning, behavioral...), and improved visualization for security incident qualification. Datalake for security incidents hunting.  
**SOAR (Security Orchestration, Automation and Response)**: Orchestration and automation of actions on security and network tools in order to reduce the Mean Time To Respond (MTTR) and alleviate the pressure on analyst workload. Guidance to decision-making thanks to predefined no-code playbooks.  
**XDR (Extended Detection & Response)**: Unification of detection tools (EDR, NDR, SIEM, SOAR...) into a single integrated package.

### Infrastructure

**VPN (Virtual Private Network)**: Secure extension of an information system over an untrusted network.  
**ZTNA (Zero Trust Network Access) = VPN++**: Enhance VPN capacities thanks to reinforced authentication and granular authorization to resources, for both remote and local users.
  
**FW (Firewall)**: Layer 3 (network layer) and layer 4 (transport layer) filtering based on explicit authorisation rules.  
**NGFW (Next Generation Firewall) = FW++**: Enhance FW capacities with deep packet inspection at layer 7 (application), and additional filtering rules such as IP geolocalsation blocking.
  
**DR (Deceptive Response)**: Honeypot aiming at luring the attackers into interacting with it. It is not used as part of nominal IT operations, so any network interaction is suspicious.

**Note:** Based on original learning material from [ANSSI](https://www.ssi.gouv.fr/) documentation *Prestataires de détection des incidents de sécurité - Référentiel d’exigences* and from [Tehtris](https://tehtris.com/) products description.
{: .notice--info}
