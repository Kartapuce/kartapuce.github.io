---
layout: single
author_profile: false
title: "NIST CSF"
excerpt: "Cybersecurity Framework"
sidebar:
  nav: "standards"
header:
  teaser: /assets/images/nist csf/csf functions.png
gallery1:
  - url: /assets/images/nist csf/csf functions.png
    image_path: assets/images/nist csf/csf functions.png
gallery2:
  - url: /assets/images/nist csf/csf profiles.png
    image_path: assets/images/nist csf/csf profiles.png
gallery3:
  - url: /assets/images/nist csf/csf tiers.png
    image_path: assets/images/nist csf/csf tiers.png
---

## Overview

The **NIST Cybersecurity Framework** is designed to help organizations to manage and reduce their cybersecurity risks. The CSF can be used to address cybersecurity risks alongside other risks of the enterprise, including those that are financial, privacy, supply chain, reputational, technological, or physical in nature.

The CSF includes:
- The **CSF Core**: a taxonomy of high-level cybersecurity outcomes that can help an organization manage its cybersecurity risks. It is a set of cybersecurity outcomes arranged by Function, then Categories, and finally Sub-Categories.
- The **CSF Organizational Profiles**: a mechanism for describing an organizational current and target cybersecurity posture in terms of the CSF Core’s outcomes.
- The **CSF Tiers**: they can be applied to CSF Organizational Profiles to characterize the rigor of an organization’s cybersecurity risk governance and management practices.

The CSF describes what desirable **outcomes** an organization can aspire to achieve, but it does not prescribe desired outcomes nor how they may be achieved. It may link to other documentation for how to achieve it.

## CSF Core Functions

The CSF Core Functions are:
- **Govern:** The cybersecurity risk management strategy, expectations, and policy are established, communicated, and monitored.
- **Identify:** The current cybersecurity risks are understood.
- **Protect:** Safeguards to manage the cybersecurity risks are used.
- **Detect:** Possible cybersecurity attacks and compromises are found and analyzed.
- **Respond:** Actions regarding a detected cybersecurity incident are taken.
- **Recover:** Assets and operations affected by a cybersecurity incident are taken.
- **Recover:** Assets and operations affected by a cybersecurity incident are restored.

{% include gallery id="gallery1" type="center" %}

## CSF Profiles and Tiers

The CSF Organizational Profile describe a **current** and **target** cybersecurity posture. They are used to understand, tailor, assess, prioritize, and communicate the CSF Core’s outcomes.
A **Community Profile** is a baseline of CSF outcomes that is created and published to address shared interests and goals for a particular sector, technology, threat type, or other use case.

An organization should go through the following steps to use an Organizational profile:

{% include gallery id="gallery2" type="center" %}

An organization can use the **Tiers** to inform its current and target profiles. The Tiers reflect an organization’s practices for managing cybersecurity risks as partial, risk-informed, repeatable, or adaptative. The Tiers should complement the risk management methodology rather than replace it.

{% include gallery id="gallery3" type="center" %}

**Note:** The CSF can be integrated with other risk management and assessment programs such as the [RMF](/standards/nist rmf) and [SP 800-30](/standards/nist sp 800 30). For an organization using the RMF, the CSF can be used to complement the RMF’s approach to selecting and prioritizing controls from the NIST SP 800-53. The CSF can be used to identify, align, and deconflict security requirements and to subsequently inform the selection of security controls for an organization. There is a traceability matrix from CSF v1.1 to SP 800-53 but it does not exist for v2 yet.
{: .notice--warning}

**Note:** Based on original learning material from [NIST](https://www.nist.gov/).
{: .notice--info}
