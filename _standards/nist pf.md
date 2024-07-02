---
layout: single
author_profile: false
title: "NIST PF"
excerpt: "Privacy Framework"
sidebar:
  nav: "standards"
header:
  teaser: /assets/images/nist pf/privacy functions.png
gallery1:
  - url: /assets/images/nist pf/security and privacy.png
    image_path: assets/images/nist pf/security and privacy.png
gallery2:
  - url: /assets/images/nist pf/privacy and risk.png
    image_path: assets/images/nist pf/privacy and risk.png
gallery3:
  - url: /assets/images/nist pf/privacy functions.png
    image_path: assets/images/nist pf/privacy functions.png
---

## Overview

Many of the benefits from Information Technology are **fueled by data** about individuals that flow through a complex ecosystem. As a result, individuals may not be able to **understand the potential consequences for their privacy** as they interact with systems, products, and services. At the same time, organizations may not realize the full extent of these consequences for individuals, for society, or their enterprises.

The purpose of the **Privacy framework** is to enable better privacy engineering practices that support privacy by design concepts and help organizations protect individuals’ privacy.

## Privacy and Security

Let's begin with a reminder about cybersecurity risks and privacy risks.

**Privacy** is the freedom from intrusion into the private life or affairs of an individual, when that intrusion results from undue or illegal gathering and use of data about that individual.

While cybersecurity and privacy are independent disciplines, **their objectives overlap** in certain circumstances:
- **Cybersecurity risks:** The loss of confidentiality, integrity, or availability of information, data, or information (or control) systems and the potential adverse impacts to organizational operations (i.e., mission, functions, image, or reputation) and assets, individuals, other organizations, and the Nation
- **Privacy risks:** The likelihood that individuals will experience problems resulting from data processing, and the impact should they occur. Many privacy risks relate to the unauthorized access or disclosure of PII, but they may also result from other activities. **Privacy events** are potential problems individuals could experience arising from operations with data, through a **complete life cycle**: collection, retention, logging, generation, transformation, use, disclosure, sharing, transmission, and disposal (referred to as data processing for a set of actions). These problems can be described as ranging from dignity-type effects such as **embarrassment** or stigmas to more tangible harms such as **discrimination**, **economic loss**, or **physical harm**.

{% include gallery id="gallery1" type="center" %}

Some examples of privacy events that are not related to cybersecurity are:
- **Aggregation of data:** online trackers are used to build a profile of your interests.
    - The privacy risk is that another person may get access to this profile and deduce information on the political opinion or religious belief.
- **Poor anonymization:** a website sells anonymized data to a third party for marketing or research purposes.
    - The privacy risk is that this data can sometimes be re-identified.
- **Excessive data collection:** an application collects the position of the user while it is not required to deliver the service.
    - The privacy risk is that another person may get access to this profile and use it for bad purposes (assault, robbery…).
- **Confidential data collection:** a fitness tracker app collects data on our daily steps and sleep patterns.
    - The privacy risk is that the data collected by the tracker may not be completely accurate, and may diagnose a wrong disease. The data may be used by an insurance company to increase the price of the insurance policy.
- **Unsecure privacy settings:** if privacy settings are complicated or not configured correctly by default, a person might be unknowingly sharing more public information than intended.
    - The privacy risk is that it may have an impact on its reputation.
    
There is a relationship between **privacy risk** and **organizational risk**:

{% include gallery id="gallery2" type="center" %}

The security objectives are determined by the CIA triad. Additional privacy capabilities can be used to describe a system that achieves the desired privacy outcome:
- **Predictability:** enabling reliable assumptions by individuals, owners, and operators about data and their processing by a system, product, or service. “Prédictibilité” pour permettre de faire des hypothèses fiables sur les PII et leur traitement.
- **Manageability:** providing the capability for granular administration of data, including alteration, deletion, and selective disclosure.
- **Disassociability:** enabling the processing of data or events without association to individuals or devices beyond the operational requirements of the system. “Disassociabilité”.

## Structure

The PF follows the same structure as the [CSF](/standards/nist csf) with the **Core** the **Profiles**, and the **Tiers**. Privacy concerns are addressed by the **privacy risk management** processes, and in particular the **privacy risk assessment** sub-process.

The **PF Core** manages privacy risks arising from data processing through 5 families:
- **Identify-P**: develop the organizational understanding to manage privacy risks for individuals arising from data processing.
- **Govern-P**: develop and implement the organizational governance structure to enable an ongoing understanding of the organization’s risk management priorities that are informed by privacy risk.
- **Control-P**: develop and implement appropriate activities to enable organizations or individuals to manage data with sufficient granularity to manage privacy risks.
- **Communicate-P**: develop and implement appropriate activities to enable organizations and individuals to have a reliable understanding and engage in a dialogue about how data are processed and associated privacy risks.
- **Protect-P**:  develop and implement appropriate data processing safeguards.

{% include gallery id="gallery3" type="center" %}

**Note:** Some functions from the CSF can be leveraged to support the management of risks associated with cybersecurity-related privacy events (e.g., privacy breaches).
{: .notice--warning}

## Crosswalks

NIST **Crosswalks** can be used to map the provisions of standards, laws or regulations and best practices to the PF activities and outcomes. For example, there are crosswalks to the General Data Protection Regulation (GDPR), the California Consumer Privacy Act (CCPA), or the NIST SP 800-53 controls.
    
**Note:** Based on original learning material from [NIST](https://www.nist.gov/).
{: .notice--info}
