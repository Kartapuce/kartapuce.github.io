---
layout: single
author_profile: false
title: "MITRE ATT&CK"
excerpt: "Knowledge base of adversary tactics and techniques"
sidebar:
  nav: "standards"
header:
  teaser: /assets/images/mitre/attack-small.png
gallery1:
  - url: /assets/images/mitre/kill chain.png
    image_path: assets/images/mitre/kill chain.png
---

## Overview

ATT&CK is a **knowledge base of adversarial tactics and techniques** based on real-world observations. It focuses on how adversaries interact with systems during an operation, reflecting the various phases of an adversary’s attack lifecycle and the platforms they are known to target.

The MITRE ATT&CK currently covers 3 technology domains:
- enterprise
- mobile :iphone:
- ICS

Each domain contains different platforms such as Windows, Linux, Cloud, Andoid, iOS.

MITRE ATT&CK can be used for several security activities such as detection, CTI, red teaming, or assessment and engineering. For example, it can be used to assess how defenses stack up to technics, and to identify gaps to tune defense. It could also be used to create operational scenarios in some risk assessment methodologies.

## Vocabulary

The **tactics** represent the **“why”** of an ATT&CK technique. It is the tactical goal. The reason for performing an action:
- reconnaissance: gather information to plan future operations :memo:
- resource development: establish resources to support operations
- initial access: get into the network :feet:
- execution: run malicious code
- persistence: maintain foothold
- privilege escalation: gain higher-level permissions :arrow_up:
- defense evasion: avoid being detected
- credential access: steal account names and passwords
- discovery: figoure out the environment
- lateral movement: move through the environment :left_right_arrow:
- collection: gather data of interest to the goal
- command and control: communicate with compromised systems to control them
- exfiltration: steal data
- impact: manipulate, interrupt, or destroy the system and data :boom:

**Note:** ATT&CK tactics and the Lockheed Martin Cyber Kill Chain are complementary. ATT&CK sits at a lower level of definition. ATT&CK tactics are unordered and may not all occur during an attack.
{: .notice--warning}

{% include gallery id="gallery1" type="center" %}

The **techniques** represent the **“how”**. It is how an adversary achieves a tactical goal by performing an action. For example, to dump credentials to achieve credential access.  
The **procedures** are specific implementation or in-the-wild use the adversary uses for techniques. For example, using PowerShell to inject into lsass.exe to dump credentials.  

In addition, the following resources can be helpful for remediation:
- The **data sources** represent the various subjects of information that can be collected by logs and sensors: firewall, active directory, application logs, network logs…  
- The **mitigations** represent security concepts that can be used to prevent a technique from being successfully executed: audit, antivirus, network segmentation…  

**Note:** Adversaries have multiple ways they can perform most techniques. The mindset and process are more important than the knowledge base. Trying to achieve 100% coverage is not the good approach.
{: .notice--warning}

**Note:** Based on original learning material from [MITRE ATT&CK](https://attack.mitre.org/) team.
{: .notice--info}
