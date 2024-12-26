---
layout: single
author_profile: false
title: "SCIM"
excerpt: "Way too many identities."
sidebar:
  nav: "protocols"
header:
  teaser: /assets/images/SCIM-small.png
gallery1:
  - url: /assets/images/SCIM.png
    image_path: assets/images/SCIM.png
---

Before we deep dive into the SCIM specification, let’s have a look at the big picture of **Identity Governance and Administration (IGA)**.

## Identity Governance and Administration (IGA)

**Identity and Access Management** ([IAM](/architecture/iam)) is the global process of managing digital identities and access to the resources. **Identity Governance and Administration** (IGA) focuses on **governance** and **compliance**, and aims at providing a clear link between digital identities and the access that are granted. It is mostly based on the concepts of:
- **Identity lifecycle** :raising_hand:
- **Access lifecycle** :lock:

**Note:** IT systems manipulate thousands of identities, which represent humans, but also services or devices. In this article, we will focus on human identities.
{: .notice--warning}

In order to illustrate the **identity lifecycle**, let’s consider the Kartapuce company. Kartapuce hires dozens of new employees per month. And since productivity and user experience are key concerns for the company, employees must have all the tools they need from Day 1. :trophy: However, they shall not have unrequired privilegies that may impact the security posture of the company.
- Alice is a new software developper for Kartapuce. Her first point of contact is the HR team, which provides the mapping of the attributes between the « physical » Alice and her « virtual » identity (*name*, *address*, *salary*, *position*…). The HR tool is a **source of truth** for Alice attributes: this is called **HR-driven inbound provisioning**. :arrow_forward:
- Based on Alice employment attributes, Kartapuce automates the identification of the tools that Alice needs for her job. The **organizational policies** are transparently inherited for each application (approbation, separation of duties, default access duration, conditional access policies…).
- A few days before Alice arrives, automated **lifecycle workflows** are executed. They can perform actions such as sending a welcoming email, or notifying the manager and the team. :email:
- On day 1, copies of her identities are created in the identity provider of Kartapuce, and within all the applications that Alice needs to perform her job. :santa: This is called **outbound app-provisionning**.

But identity is a moving concept! :repeat:
- If Alice moves to a new address, gets promoted, or decides to leave the company, the whole identity lifecycle workflow gets executed again, and **changes are instantaneously replicated** across all systems. It is paramount that Alice identity remains the same across all systems in order to ensure **consistency of information**.
- When Kartapuce gets **audited**, the listings of all the users of each application are extracted, and all the access modifications performed automatically during the audit period are clearly registered. :mag:

## SCIM provisioning

Now that we understand the (not so) perfect world of identity governance, let’s get back to **SCIM provisionning**!

The **System for Cross-domain Identity Management (SCIM)** specification sets a standard for managing identity lifecycle across applications. A SCIM compliant endpoint exposes a REST API that respects the SCIM specification. This speification is based on the concepts of **resources** (users or groups) encoded in JSON format, and **operations** (*create*, *read*, *replace*, *delete*, *update*, *search*, *bulk*).

**Note:** The SCIM specification specifically adresses the concepts of provisionning and **identity lifecycle**.  It does not directly addess access lifecycle, which focuses on enforcing access control. This can be achieved with other protocols such as [SAML](/protocols/saml) or [OIDC](/protocols/openID connect). But we won’t detail that in this article! :sunglasses:
{: .notice--warning}

{% include gallery id="gallery1" type="center" %}

**Note:** Based on original learning material from [Microsoft](https://learn.microsoft.com/en-us/entra/id-governance/identity-governance-overview) engineers.
{: .notice--info}
