---
layout: single
author_profile: false
title: "CIS 18"
excerpt: "CIS 18 Critical Security Controls"
sidebar:
  nav: "standards"
header:
  teaser: /assets/images/cis 18/cis 18 assets-small.png
gallery1:
  - url: /assets/images/cis 18/cis 18 safeguard.png
    image_path: assets/images/cis 18/cis 18 safeguard.png
gallery2:
  - url: /assets/images/cis 18/cis 18 assets.png
    image_path: assets/images/cis 18/cis 18 assets.png
---

## Overview

The **CIS Critical Security Controls** (CIS 18) are a prioritized set of CIS Safeguards to mitigate the most common cyber-attacks against systems and networks.

## The CDM approach

The *CIS 18* controls are meant to be a highly efficient set of **defensive actions**, and not just another listing of good things to do. How did they select the controls then?! :stuck_out_tongue_winking_eye: The answer relies on a data-driven approach: the **Community Defense Model** (*CDM*). The CDM experts identified the top 5 attacks from data sources, such as the *Verizon DBIR* and the *ENISA Threat Landscape* reports:
- Malware
- Ransomware :moneybag:
- Web Application Hacking
- Insider and privilege misuse :smiling_imp:
- Targeted intrusions
    
Then they identified the attack patterns used in each attack type, as modelled in the [MITRE ATT&CK](/standards/mitre attack) knowledge base. Finally, they identified the coverage of these techniques by the CIS 18 safeguards.

**Note:** The IG1 safeguards protects against the top five attack types, and covers 77% of the MITRE ATT&CK sub-techniques!
{: .notice--warning}

## The CIS 18 spirit

We can find dozens of lists of efficient security recommendations. The real value of the CIS 18 Controls is the **feedback from cybersecurity experts**. How can I get trained? :books: How others have implemented these controls? Is there a tool available? CIS 18 provides mappings to other risk management frameworks ([NIST CSF](/standards/nist csf), ISO 27001…) and regulations (PCI DSS, HIPAA…). CIS also includes the **CIS Benchmarks**, with security baselines for cloud providers, OS, software… Finally, CIS offers a **Self-Assessment Tool** (CIS CSAT), but you got to be a CIS member to read it! :sob:

## Implementation Groups

The CDM answers to the question “*How effective are my controls against the most prevalent current attacks?*”. The Implementation Groups IGs answer to the question “*What shall I do first?*”. :point_up:
The CIS 18 controls are built around the notion of **Implementation Groups** (CIS 18 IGs) to prioritize implementation. It helps companies to determine the actions that they shall prioritize:
- **IG1** for enterprises with limited IT and cybersecurity expertise :baby:
- **IG2** for enterprises that employ individuals responsible for managing and protecting IT infrastructure
- **IG3** for enterprises that employ many cybersecurity experts specialized in the different facets of cybersecurity. :factory:

## CIS 18 Controls

The CIS 18 contains 18 Security Controls:
- **Control 1:** Inventory and Control of Enterprise Assets
- **Control 2:** Inventory and Control of Software Assets
- **Control 3:** Data Protection :file_folder:
- **Control 4:** Secure Configuration of Enterprise Assets and Software
- **Control 5:** Account Management
- **Control 6:** Access Control Management
- **Control 7:** Continuous Vulnerability Management
- **Control 8:** Audit Log Management :mag:
- **Control 9:** Email and Web Browser Protections :email:
- **Control 10:** Malware Defenses
- **Control 11:** Data Recovery
- **Control 12:** Network Infrastructure Management
- **Control 13:** Network Monitoring and Defense :paw_prints:
- **Control 14:** Security Awareness and Skills Training
- **Control 15:** Service Provider Management
- **Control 16:** Application Software Security
- **Control 17:** Incident Response Management
- **Control 18:** Penetration Testing :gun:

**Note:** This article is based on CIS 18 v8.1. No doubt a new version will be available as you read this. :fire:
{: .notice--warning}

Each control is made up of multiple **safeguards**. And each safeguard is mapped with:
- An **asset type** applicable to the safeguard
- A **security function** as identified in the [NIST CSF](/standards/nist csf)
- An **Implementation Group**
    
Here is an extract for reference!

{% include gallery id="gallery1" type="center" %}

## Asset types

CIS 18 provides a modelling of the different **types of assets** used in a company. It's a gold mine! :hearts:

{% include gallery id="gallery2" type="center" %}

**Note:** Based on original learning material from [CIS 18](https://www.cisecurity.org/controls). The CIS 18 licence is available [here](https://creativecommons.org/licenses/by-nc-nd/4.0/legalcode).
{: .notice--info}
