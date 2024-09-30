---
layout: single
author_profile: false
title: "NIST SP 800-39"
excerpt: "Managing Information Security Risk - Organization, Mission, and Information System View"
sidebar:
  nav: "standards"
header:
  teaser: /assets/images/nist sp 800 39/risk management process.png
gallery1:
  - url: /assets/images/nist sp 800 39/risk management process.png
    image_path: assets/images/nist sp 800 39/risk management process.png
gallery2:
  - url: /assets/images/nist sp 800 39/multitiered risk.png
    image_path: assets/images/nist sp 800 39/multitiered risk.png
---

## Overview

Organizations depend on information systems to successfully carry out their mission and business functions. **Information systems** are subject to **threats** that can have **adversarial effects** on operations, assets, individuals, and other organizations. Leaders and managers **at all level** must understand their responsibilities and be held accountable for managing information security risk.

Organizational risks include **many types of risks** (program management risk, investment risk, budgetary risk, safety risk, security risk, supply chain risk…). Managing information security risk is not an exact science. It brings together the best collective judgement of individuals and groups within an organization.

NIST SP 800-39 purpose is to provide guidance for managing information security risk.

**Note:** [NIST SP 800-30](/standards/nist sp 800 30) amplifies the guidance of SP 800-39 by providing guidance for conducting risk assessments, which is one of the fundamental components of an organizational risk management process.
{: .notice--warning}

## Components of risk management

**Risk management** is a comprehensive process that requires organizations to:
- **Frame risk:** establish a risk context which describes the environment in which risk-based decisions are made. The purpose is to produce a risk management strategy that describe how organizations intend to assess risk, respond to risk, and monitor risk. Organizations should identify risk assumptions (about the threats, vulnerabilities…), risk constraints, risk tolerance, and priorities and trade-off. The risk framing component should be managed by **senior leaders**.
- **Assess risk:** it addresses how to assess risk within the context of the organizational risk frame. The reader may refer to NIST SP 800-30.
- **Respond to risk:** it addresses how organizations respond to risk once that risk is determined based on the result of risk assessments. The purpose it to provide a consistent response to risk by developing alternative courses of action for responding to risk; evaluating the alternative courses of action; determining appropriate courses of actions consistent with organizational risk tolerance; implementing risk responses based on selected courses of action. The types of risk responses that can be implemented are:
    - accept
    - avoid
    - mitigate
    - share
    - transfer
- **Monitor risk:** The purpose is to verify that planned risk response measures are implemented and information security requirements are satisfied; determining the ongoing effectiveness or risk response measures following implementation; identifying risk-impacting changes to organizational information systems and the environments in which the system operate.

{% include gallery id="gallery1" type="center" %}

**Note:** Each of these 4 steps in the risk management process applies to the 3 tiers. These steps are not inherently sequential in nature.
{: .notice--warning}

## Multitiered risk management

To integrate the risk management process throughout the organization, a three-tiered approach is employed that addresses risk at the:
- **Organizational level (tier 1):** it implements the first components of risk management (framing), by providing the context for all risk management activities. For example, it provides a prioritization of mission functions (which derives in development of programs); or includes the selection of common controls. Tier 1 establishes and maintains governance structures, which provide oversight for the risk management activities conducted by organizations. It includes the establishment and implementation of a risk executive (function); the determination of a risk management strategy including the determination of a risk tolerance; the development and execution of investment strategies for information resources and information security. In particular, Tier 1 shall determine the types of risk management decisions that are reserved for specific leadership roles; the types of risk management decisions that are deemed to be organization-wide and those that can be delegated to subordinate organizations.
- **Mission/business processes (tier 2):** defining the mission processes needed to support the business functions of organizations; prioritizing the mission processes with respect to the strategic goals of the organization; defining the types of information needed to successfully execute the mission processes; incorporating information security requirements into the mission processes; establishing an enterprise architecture.
- **Information systems (tier 3):** categorizing organizational information systems; allocating security controls to organizational information systems; managing the selection, implementation, assessment, authorization and ongoing monitoring of security controls.

{% include gallery id="gallery2" type="center" %}

**Note:** The [RMF](/standards/nist rmf) is the primary means for addressing risk at tier 3.
{: .notice--warning}

## Trust and trustworthiness

**Trust** is an important concept related to risk management. The **reliance on information system services and external organizations** as well as partnerships to accomplish mission functions, result in the need for **trust relationships** between organizations. In many cases, trust relationships with external organizations, while generating greater productivity and cost efficiencies, can also bring greater risk to organizations. This risk is addressed by the risk management strategy by defining the types of service / information to be provided; establishing the degree of control over the partner; describing how the information is protected; obtaining the relevant information to determine trustworthiness; determining if the ongoing risk is at an acceptable level.

The concept of **trustworthiness** can also be applied to information technology products. Trustworthiness expresses the degree to which information systems (including the information technology products from which the systems are built) can be expected to preserve the confidentiality, integrity, and availability of the information being processed, stored, or transmitted by the systems across the full range of threats. Two factors affecting the trustworthiness are:
- **Security functionality** (the security features employed within the system). It can be obtained by employing a combination of management, operational, technical controls such as those from NIST SP 800-53.
- **Security assurance** (grounds for confidence that the security functionality is effective in its application). It can be obtained by the actions taken by developers and implementers and assessors.  

Information technology products and systems exhibiting a higher degree of trustworthiness are expected to exhibit a lower rate of latent design and implementation flaws and a higher degree of penetration resistance against a range of threats.

## Organizational culture

**Organizational culture** refers to the **values, beliefs and norms** that influence the behaviors and actions of the senior leadership and individual members of an organization. It describes the way things are done in an organization, and can explain why certain things occur. There is a **direct relationship** between organizational culture and how organizations respond to uncertainties and the potential for near-term benefits to be the source for longer-term losses. The organization’s culture informs and even defines that organization’s risk management strategy. Culture both shapes and is shaped by the people within organizations.

**Note:** Based on original learning material from [NIST](https://www.nist.gov/).
{: .notice--info}

