---
layout: single
author_profile: false
title: "Secure Access Service Edge"
excerpt: "Move your secure gateway to the cloud."
sidebar:
  nav: "architecture"
header:
  teaser: /assets/images/SASE.png
gallery1:
  - url: /assets/images/SASE.png
    image_path: assets/images/SASE.png
---

**Secure Access Service Edge (SASE)** is a cloud-based IT model which bundles together Network-as-a-Service features with Network-Security-as-a-Service functions. This architecture is part of the transition from an outdated Castle-and-Moat architecture (not adapted to cloud hosting) to a Zero Trust model.
- **Network-as-a-Service (NaaS)** is the provision of network services from a cloud provider. It aims at replacing private VPNs and MPLS connections. It relies a lot on Software Defined Networking technologies.
- **Network-Security-as-a-Service (NSaaS)** is the provision of network security services from a cloud provider. The security aspect of SASE is also called **Security Service Edge (SSE)**.

{% include gallery id="gallery1" type="center" %}

**Note:** A Wide Area Network (WAN) connects Local Area Networks (LANs) across long distances. In order to speed up connections, many companies use specific **Multi Protocol Label Switching (MPLS)** hardware instead of classic routing.
{: .notice--warning}

**Note:** Based on original learning material from [Cloudflare](https://www.cloudflare.com/learning) engineers.
{: .notice--info}
