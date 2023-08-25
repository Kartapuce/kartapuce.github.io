---
layout: single
author_profile: false
title: "Detection and Response"
excerpt: "What's going on in my realm?"
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

**NIDS** (*Network Intrusion Detection System*): Static signature-based detection of known malware patterns. It interfaces with the network through port-mirroring or a TAP.  
**NTA** (*Network Traffic Analysis*) **= NIDS++**: Enhance NIDS capacities with dynamic anomaly-based detection, a.k.a. behavior-based detection, focusing on deviations from nominal traffic. It may also offer additional features such as netflow capture, full packet capture, passive vulnerability scanning, or shadow IT detection.  
**NDR** (*Network Detection & Response*) **= NTA++**: Enhance NTA capacities with incident response playbooks and automatic remediation.

### Endpoint tools

**AV** (*Antivirus*): Static signature-based detection through comparison with a set of known malwares.  
**EPP** (*Endpoint Protection Platform*) **= AV++**: Enhance AV capacities with dynamic heuristic analysis (detection of malware operations on the system) in order to better detect unknown variants. It is still quite easy to bypass as it is based on analysis of known malwares.  
  
**HIDS** (*Host Intrusion Detection System*): Dynamic rule-based detection of malware variants through monitoring of endpoint operations (processes, logs, network connections, registers...).  
**EDR** (*Endpoint Detection & Response*) **= HIDS++**: Enhance HIDS with anomaly-based detection (behavioral-based detection). It improves unknown malwares detection (0-day malware) by analysing deviations from nominal operations on the endpoint, often relying on machine-learning technologies. It may also offer vulnerability scanning, and automated response to security incidents.

### Analysis tools

**SIEM** (*Security Information and Event Management*): Centralization of security events, advanced analysis features (correlation, machine learning, behavioral...), and improved visualization for security incident qualification. Datalake for security incidents hunting.  
**SOAR** (*ecurity Orchestration, Automation and Response*): Orchestration and automation of actions on security and network tools in order to reduce the Mean Time To Respond (MTTR) and alleviate the pressure on analyst workload. Technical guidance during incident response operations thanks to predefined no-code playbooks.  
**XDR** (*Extended Detection & Response*): Unification of detection tools (EDR, NDR, SIEM, SOAR...) into a single integrated package.

### Infrastructure

**VPN** (*Virtual Private Network*): Secure extension of an information system over an untrusted network.  
**ZTNA** (*Zero Trust Network Access*) **= VPN++**: Enhance VPN capacities thanks to reinforced authentication, and granular authorization to resources, for both remote and local users.
  
**FW** (*Firewall*): Layer 3 (network layer) and layer 4 (transport layer) filtering based on explicit authorisation rules.  
**NGFW** (*Next Generation Firewall*) **= FW++**: Enhance FW capacities with Layer 7 (application) deep packet inspection. It may also offer additional filtering features such as IP geolocalisation blocking.
  
**DR** (*Deceptive Response*): Honeypot aiming at luring the attackers into interacting with it. It is not used as part of nominal IT operations, so any network interaction is suspicious.

**Note:** Based on original learning material from [ANSSI](https://www.ssi.gouv.fr/) documentation *Prestataires de détection des incidents de sécurité - Référentiel d’exigences* and from [Tehtris](https://tehtris.com/) products description.
{: .notice--info}
