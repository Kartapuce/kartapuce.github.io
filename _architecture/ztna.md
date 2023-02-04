---
layout: single
author_profile: false
title: "Zero Trust Network Access"
excerpt: "Discover all the benefits from ZTNA."
sidebar:
  nav: "architecture"
header:
  teaser: /assets/images/ztna/vpn.png
gallery1:
  - url: /assets/images/ztna/vpn.png
    image_path: assets/images/ztna/vpn.png
gallery2: 
  - url: /assets/images/ztna/nac.png
    image_path: assets/images/ztna/nac.png
gallery3: 
  - url: /assets/images/ztna/ztna.png
    image_path: assets/images/ztna/ztna.png
---

## Legacy Virtual Private Network (VPN) Remote Access

In a traditional castle-and-moat architecture, remote users often get access to the internal network through a **Virtual Private Network (VPN)**.
- Authorized users own a VPN client, granting them secure access to the internal network. But once connected, every user has access to all the internal network ! It’s open-bar for the remote user, but also for an attacker who may easily perform lateral movement. Depending on the VPN technology, the attacker has full knowledge of internal network from layer 2, or 3, up to layer 7.
- Furthermore, all remote users are treated the same way. If users with different profiles need to access remotely their subnet (admin, dev, test…), it is required to set up different VPN terminations. In most cases, VPN terminations are hosted on-premise, making it hard to scale-up, and creating sluggish performance.
- Note that some venders now sell VPN terminations as virtual machines hosted in the cloud. But anyway, it remains inefficient for roaming users who frequently switch between wireless access points, breaking the VPN set up.

{% include gallery id="gallery1" type="center" %}

## Legacy Local Network Access Control (NAC)

In a traditional castle-and-moat architecture, internal users of the network are often treated differently from remote users. They are granted access to the internal network only if the **Network Access Control (NAC)** authentication is successful. A Radius server often provides this feature. Once the user is authorized inside, he often faces a flat network with no internal segmentation. And that again, is open-bar for any attacker!

{% include gallery id="gallery2" type="center" %}

## Cloud-hosted Zero Trust Network Access (ZTNA)

Zero Trust Network Access is a core component of the Zero Trust design pattern, which states that the level of threat is identical both inside and outside the network.
- All users, whether they are out-of-the-office, or directly connected to the internal network, are treated the same way, with the same level of authentication and permissions. With some magic that is for me hard to figure out, a thin segmentation is implemented, and authenticated users can only get access to the resources they are authorized to use.
- This access control is performed at the application layer, and it can be enhanced with device security posture analysis, or end-user behaviour metrics.
- ZTNA is one kind of implementation of **Software Defined Perimeter (SPD)**, which aims at achieving some kind of virtual secure border between the external world and available applications, making abstraction of the physical hardware used for connectivity (routers, firewall…). The ZTNA can also be hosted on premise for businesses with geopolitical requirements, but it would not benefit from the scalability and availability of cloud hosted services.

{% include gallery id="gallery3" type="center" %}

**Note:** Based on original learning material from [Cloudflare](https://www.cloudflare.com/learning) engineers.
{: .notice--info}
