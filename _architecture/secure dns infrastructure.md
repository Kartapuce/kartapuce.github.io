---
layout: single
author_profile: false
title: "Secure DNS infrastructure"
excerpt: "Everything you've always wanted to know about DNS."
sidebar:
  nav: "architecture"
header:
  teaser: /assets/images/Secure DNS infrastructure.png
gallery1:
  - url: /assets/images/Secure DNS infrastructure.png
    image_path: assets/images/Secure DNS infrastructure.png
---

## Architecture

This modelling aims at describing the different components that are part of a **Domain Name System (DNS)** infrastructure, and their location within a secure gateway.

:x: It highlights several well-known attacks on a DNS infrastructure:
- DNS cache poisoning / DNS spoofing
- DNS tunneling
- DNS hijacking
- DNS flooding
- DNS zone transfer
- DNS data tampering
- DNS loss of availability
- dangerous browsing.

:heavy_check_mark: And it identifies the means to protect:
- extended TTL and DNS over TCP
- DNS filtering
- DNS over TLS
- DoS protection
- DNSSEC
- DNS redundancy
- DNS firewall.

## Use Case

In this example, let's consider the user Alice. She is a valuable member of Kartapuce, and belongs to the kartapuce.com domain. Since she knows where to find instructive information, she wants to browse to the [ANSSI](https://www.ssi.gouv.fr/) website.

Then Alice learnt so many things, she must ping Bob who is also a member of the internal kartapuce.com domain.

Let's have a look at all the operations that happen under the wood ! :stuck_out_tongue:

{% include gallery id="gallery1" type="center" %}

**Disclaimer:** These are obviously not the real architecture and IP addresses for reaching out to the ANSSI !
{: .notice--warning}

**Note:** Based on original learning material from [ANSSI](https://www.ssi.gouv.fr/) documentation *Bonnes pratiques pour l'acquisition et l'exploitation de noms de domaine*.
{: .notice--info}
