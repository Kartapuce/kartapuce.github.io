---
layout: single
author_profile: false
title: "NIST RMF"
excerpt: "Risk Management Framework"
sidebar:
  nav: "standards"
header:
  teaser: /assets/images/nist sp 800 37/rmf framework.png
gallery1:
  - url: /assets/images/nist sp 800 37/rmf framework.png
    image_path: assets/images/nist sp 800 37/rmf framework.png
---

## Overview

The **Risk Management Framework** (NIST SP 800-37) is a framework to achieve an **effective** (producing a result that is wanted), **efficient** (without wasting time, material…), and **cost-effective** security and privacy Risk Management Process.

The RMF is **technology neutral**: it is possible to change the selection of controls, their implementation details, and assessment methods, but there is no need to adjust the RMF process to accommodate specific technologies. The RMF is applied **iteratively** during the system development lifecycle. The security and privacy requirements and controls are implemented, verified, and validated continuously.

The RMF uses a **unified approach for security and privacy**. The purpose is to maximize efficiency and reduce duplication of effort. In the end, it is not about generating additional paperwork, artifacts… But it is about ensuring greater visibility into the implementation of security and privacy controls, to promote more informed, risk-based authorizations.

## Back to basics

It never hurts to go back to some basic definitions!

**Information security** is the protection of information and information systems from unauthorized access, use, disclosure, disruption, modification, or destruction (i.e., unauthorized system activity or behavior) in order to provide **confidentiality**, **integrity**, and **availability**.

Information security can be achieve by combining several **types of protective measures**:
- corrective,
- compensating
- detective
- deterrent
- directive
- preventative
- recovering

These controls can belong to different **categories**:
- physical,
- administrative,
- technical.

Let's clarify the CIA triad:
- **Confidentiality:** ensure that only authorized individuals or systems have access to specific information and that it is not disclosed to anyone who shouldn’t see it.
- **Integrity:** protect information from unauthorized modification, deletion, or manipulation. The purpose is to ensure through the lifecycle of information:
    - **Accuracy:** the data is correct and reflects the reality. There are no missing values or empty fields that would hinder analysis or decision making.
    - **Completeness:** all the necessary data is present and accounted for.
    - **Consistency:** the data follows consistent rules and definitions throughout the system. Similar data points are represented the same way across different records and applications.
- Information integrity includes:
    - **Authenticity:** The property that data originated from its purported source.
    - **Non-repudiation:** Provide assurance of the origin and integrity of data in such a way that the integrity and origin can be verified and validated by a third party as having originated from a specific entity; provide assurance that a sender and a recipient can later never denied having processed the information.
- **Availability:** the data is accessible and retrievable whenever and wherever it’s needed by authorized users or systems.

## Organization wide risk management

The RMF mostly applies to the **level 3** of the multitier risk management approach described in [NIST SP 800-39](/standards/nist sp 800 39). However, Level 1 and level 2 prepare the organization for the execution of the RMF. The risk decisions at level 1 and level 2 can impact the selection of controls at the system level. Otherwise, security and privacy activities can become too costly, demand too many skilled security and privacy professionals, and produce ineffective solutions.

There is flexibility in the RMF process. Organizations can change the order of tasks, emphasize on some tasks, or combine them. Flexibility also happens in control selection and control tailoring (customize for the specific missions, business functions, risks, and operating environments of the system), and control assessment.

**Note:** The RMF aligns with the [CSF](/standards/nist csf). Many RMF tasks have a reference to the corresponding CSF function.
{: .notice--warning}

## RMF steps and structure

The RMF requires 1 **preparatory step** and 6 **main steps**:
- **Prepare** to execute the RMF from an organization and system level perspective by establishing a context and priorities for managing security and privacy risks
- **Categorize** the system and the information processed, stored, and transmitted by the system based on an analysis of the impact of loss
- **Select** an initial set of controls for the system and tailor the controls as needed to reduce risk to an acceptable level based on an assessment of risk. Controls are system-specific, hybrid or common (inherited). Organizations shall establish traceability of controls to the security and privacy requirements that the controls are intended to satisfy.
- **Implement** the controls and describe how the controls are employed within the system and its environment of operation
- **Assess** the controls to determine if the controls are implemented correctly, operating as intended, and producing the desired outcomes with respect to satisfying the security and privacy requirements
- **Authorize** the system or common controls based on a determination that the risk to organizational operations and assets, individuals, other organizations and the Nation is acceptable
- **Monitor** the system and the associated controls on an ongoing basis to include assessing control effectiveness, documenting changes to the system and environment of operation, conducting risk assessments and impact analysis, and reporting the security and privacy posture of the system

{% include gallery id="gallery1" type="center" %}

Each step of the RMF has:
- A purpose statement
- A defined set of outcomes
- A set of tasks that are carried out to achieve those outcomes

<div class="notice--warning" markdown="1">   
**Note:** It is important to understand the concept of requirements and controls.
- **Requirements:** A combination of:
    - Legal and policy requirements (obligation imposed on organizations)
    - An expression of the set of stakeholder protection needs for a particular system or organization
- **Controls:** description of the safeguards and protection capabilities appropriate for achieving the particular security and privacy objectives of the organization and reflecting the protection needs of the stakeholders. Controls are selected and implemented by the organization in order to satisfy the system requirements.
</div>

**Note:** Based on original learning material from [NIST](https://www.nist.gov/).
{: .notice--info}
