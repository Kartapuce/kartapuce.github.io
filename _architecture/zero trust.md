---
layout: single
author_profile: false
title: "Zero Trust"
excerpt: "A long journey towards Zero Trust."
sidebar:
  nav: "architecture"
header:
  teaser: /assets/images/zero trust-small.png
gallery1:
  - url: /assets/images/zero trust.png
    image_path: assets/images/zero trust.png
---

Let's put some segmentation in our network, and review all the steps towards **Zero Trust**:
- Open network: *That's just Open-bar man!* :beer:
- Perimeter-based segmentation: *IPsec, 802.1X, and we're good to go.*
- Macro-segmentation: *Choose your VLAN wisely.* :detective: 
- Clustered segregation: *So much stuff behind that wall.*
- Micro-segmentation: *Let's get selective.*
- Zero Trust: *I just don't care where you are.* :dart:

**Note:** Each step provides cumulative additional protections to enforce.
{: .notice--warning}

The blue zone represents the trusted area. The black line demarcates the internal network. The Firewall icon represents the authentication and authorization process.

{% include gallery id="gallery1" type="center" %}

**Note:** A review of the migration towards Zero Trust has been performed by the [ANSSI](https://www.ssi.gouv.fr/agence/publication/le-modele-zero-trust/).
{: .notice--info}

## Zero Trust principles

**Before:** Traditional IT systems only rely on perimeter security. Firewalls control the exposed interfaces, and a few VPN gateways permit to enter the internal network. Any internal user or component is given implicit trust, and is granted access to all the resources.

**However:** This architecture creates operational issues, since the infrastructure is not adapted to modern needs (remote workers and offices, services hosted in the cloud…). VPN gateways are accountable for latency issues due to poor scalability to handle bursts of traffic.

**And:** Lateral movement within the inner system is trivial due to implicit trust: if one component is successfully attacked, the full IT system is compromised.

**Therefore:** A new paradigm emerges, focusing on subjects (human or machines) and resources (data, applications, infrastructure components…), instead of physical location. The Zero Trust strategy asserts that all the users are potentially malicious (internal or external) and that the full environment is intrinsically hostile (devices, applications…). Denying all access is the default state, so any open dataflow must be strictly required (dynamic least privilege), and explicitly authenticated and authorized. The IT system is probably already compromised, and all logs and behaviours must be scrutinized.

**How:** The security measures concern the users (Multi-Factor Authentication MFA, Privileged Access Management PAM, dynamic authorizations), the devices (Trusted Platforms Modules TPM, Mobile Device Managers MDM), the network (macro and micro segmentation), the applications (DevSecOps, security of the supply chain), the data (encryption in transit and at rest, granular access control, Data Rights Management DRM), the monitoring (data collection, processing, and visualization), the operations (automation, governance, centralization). These are examples of security functions and operations, but simply ticking the box won’t work. Zero Trust, Agility… one shall always stick to the core principles to assess the maturity of an organization.

**Note 1:** Zero Trust is not an architecture. It is a set of guiding principles for building an architecture and specifying operational procedures.  
**Note 2:** Transitioning to Zero Trust is often an incremental process. Most companies operate in a hybrid Zero Trust / Perimeter-based mode.
{: .notice--warning}

**Note:** A review of the migration towards Zero Trust has been performed in the *Department of Defense (DoD) Zero Trust Reference Architecture* and the *NIST SP 800-207 Zero Trust Architecture*.
{: .notice--info}
