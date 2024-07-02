---
layout: single
author_profile: false
title: "NIST SP 800-30"
excerpt: "Guide for Conducting Risk Assessments"
sidebar:
  nav: "standards"
header:
  teaser: /assets/images/nist sp 800 30/risk model.png
gallery1:
  - url: /assets/images/nist sp 800 30/risk model.png
    image_path: assets/images/nist sp 800 30/risk model.png
gallery2:
  - url: /assets/images/nist sp 800 30/risk assessment process.png
    image_path: assets/images/nist sp 800 30/risk assessment process.png
---

## Overview

**Risk Assessment** is a part of a risk management program. It facilitates decision making at all three tiers of the risk management hierarchy (organization, mission / business, information system). Risk assessments can be conducted throughout the SDLC, in order to **identify, estimate and prioritize risk**.

**Note:** NIST SP 800-30 focuses on risk assessment. For guidance on the whole risk management process, refer to [NIST SP 800-39](/standards/nist sp 800 39).
{: .notice--warning}

A **risk assessment methodology** typically includes:
- a risk model
- an assessment approach
- an analysis approach
- a risk assessment process

## Risk model

A **Risk Model** defines the risk factors to be assessed and the relationship among those factors. Typical risk factors include threat, vulnerability, impact, likelihood, and predisposing condition.

Let's start with some definitions:
- **Risk:** it is a measure of the extent to which an entity is threatened by a potential circumstance or event. It is a function of the likelihood of a threat event’s occurrence and potential adverse impact should the event occur.
- **Risk assessment:** it is the process of identifying, estimating, and prioritizing information security risks.
- **Threat:** it is any circumstance or event with the potential to adversely impact organizational operations and assets, individuals, or other organization through an information system with unauthorized access, destruction, disclosure or modification of information, and denial of service.
- **Threat events:** the intent and method targeted at the exploitation of a vulnerability, or a situation and method that may accidentally exploit a vulnerability. Threat events are caused by threat sources.
- **Threat scenario:** it is a set of discrete threat events, ordered in time, that result in adverse effects.
- **Vulnerability:** it is a weakness in an information system, system security procedures, internal controls, or implementation that could be exploited by a threat source.
- **Likelihood of occurrence:** a weighted risk factor based on an analysis of the probability that a given threat is capable of exploiting a given vulnerability. It is typically based on adversary intent, adversary capability, and adversary targeting.
- **Impact from a threat event:** the magnitude of harm that can be expected to result from the consequences of unauthorized disclosure of information, modification, destruction, loss of availability.

{% include gallery id="gallery1" type="center" %}

**Note:** Uncertainty is inherent in the evaluation of risk. Uncertainty is caused by limitations on the extent to which the future will resemble the past; imperfect or incomplete knowledge of the threat, undiscovered vulnerabilities in technologies or products, and unrecognized dependencies. The degree of uncertainty can be communicated in the form of the results.
{: .notice--warning}

## Assessment approach

There are 3 types of assessment approach:
- **Quantitative assessment:** assess risk based on the use of numbers. It effectively supports cost-benefice analysis, but may not always be clear.
- **Qualitative assessment:** assess risk based on non-numerical categories or levels (very low, low, moderate, high, very high). It effectively supports communicating risk results to decision makers, but it could produce significantly different assessment results if each value is not well defined.
- **Semi-quantitative:** assess risk using bins, scales, or representative numbers (e.g. 1 – 10 scale). It easily translates into qualitative terms, and permits easier comparisons.

## Analysis approach

There are different types of analysis approach:
- **Threat-oriented:** Start with the identification of threat sources and threat events, and focus on the development of threat scenarios. Vulnerabilities are identified in the context of threats, and then impact are identified based on adversary intent.
- **Asset / Impact-oriented:** Start with the identification of impacts or consequences of critical assets (based on BIA), and identify threat events that could lead to that impact (and threat sources that could seek these consequences).
- **Vulnerability-oriented:** Start with a set of exploitable weaknesses or deficiencies, and identify threat events that could exercise those vulnerabilities together with possible consequences of vulnerabilities being exercised.

In addition to the analysis approach, organizations may apply more rigorous analysis techniques (such as graph-based analysis) to account for the many-to-many relationship between threat events and threats sources; threat events and vulnerabilities; threat events and impacts.

**Note:** Risk assessment can be integrated with the steps of the [RMF](/standards/nist rmf). The RMF, in its SDLC approach, operates primarily at Tier 3, but with some applications at tiers 1 and 2 (selection of control for example). The Risk Assessment can be tailored to each step in the RMF. For example, to select the additional controls that complement the control baseline. Or to identify alternative implementations of selected controls. Or the RMF assessment can be an input to identify vulnerabilities.
{: .notice--warning}

## The Risk assessment process

The process of assessing information security risk is composed of 4 steps:
- **Prepare for the assessment:** establish a context for the risk assessment (purpose, scope, assumptions and constraints, sources of information used as inputs, risk model and analytic approach to use).
- **Conduct the assessment:** produce a list of information security risks that can be prioritized by risk level and used to inform risk response decisions. Identify threat sources that are relevant to the organization. Identify threat events that could be produced by threat sources. Identify vulnerabilities that could be exploited by threat sources through specific threat events. Determine the likelihood that the identified threat sources would initiate specific threat events, and the likelihood that threat events would be successful. Determine the adverse impact resulting of the exploitation of vulnerabilities by threat sources. Determine information security risks as combination of likelihood of threat exploitation of vulnerabilities and the impact of such exploitation.
- **Communicate results**
- **Maintain assessment:** support the ongoing review of risk management decisions. On an ongoing basis, determine the effectiveness of risk response, identify risk-impacting changes, and verify compliance.

{% include gallery id="gallery2" type="center" %}

**Note:** this 4-step assessment process is consistent with the general risk assessment process of [NIST SP 800-39](/standards/nist sp 800 39).
{: .notice--warning}

## Appendix

**Threat sources** can be of type:
- Adversarial: outsider, insider, trusted insider, privileged insider, supplier, partner, customer, nation…
- Accidental: user, administrator… (erroneous action taken by individuals in the course of executing their everyday responsibilities)
- Structural: storage, processing, sensor, OS, networking… (failure of equipment or software, due to aging, resource depletion…)
- Environmental: natural or man-made disaster such as fire, flood, hurricane; infrastructure failure such as telecommunications (on which the organization depends, but which are outside the control of the organization)

The adversarial threat sources have several characteristics such as:
- Capability (level of expertise and resources)
- Intent (brutally disrupt, vs quietly take control)
- Targeting (wide attack, vs specific target)

**Threat events** can be of type adversarial (expressed as tactics, techniques and procedures TTPs) or non adversarial.

Adversarial threat events can be at all steps of the cyber kill chain, for example:
- Perform network sniffing
- Craft phishing attacks
- Deliver malware by providing removable media
- Exploit recently discovered vulnerabilities
- Conduct DoS attack
- Conduct bruteforce loging
- Obtain sensitive information via exfiltration
- Obtain unauthorized access

Non adversarial threat events can be:
- Mishandling of sensitive information by authorized user
- Incorrect privilege settings
- Flood at primary facility
- Disk error
Each threat event comes with a relevance: N/A, possible, predicted, anticipated, expected, confirmed.

**Note:** Based on original learning material from [NIST](https://www.nist.gov/).
{: .notice--info}

