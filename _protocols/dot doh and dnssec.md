---
layout: single
author_profile: false
title: "DoT, DoH and DNSSEC"
excerpt: "I'll never trust that DNS cache!"
sidebar:
  nav: "protocols"
header:
  teaser: /assets/images/dnssec/dnssec-small.png
gallery1:
  - url: /assets/images/dnssec/dns.png
    image_path: assets/images/dnssec/dns.png
gallery2:
  - url: /assets/images/dnssec/dot.png
    image_path: assets/images/dnssec/dot.png
gallery3: 
  - url: /assets/images/dnssec/doh.png
    image_path: assets/images/dnssec/doh.png
gallery4: 
  - url: /assets/images/dnssec/dnssec.png
    image_path: assets/images/dnssec/dnssec.png
---

## DoT and DoH

The [DNS](/architecture/secure dns infrastructure) protocol used for domain name resolution is **natively insecure**. :sob: It is built upon UDP datagrams sent on port 53 of DNS servers. Therefore, it does not authenticate the destination server, and all the data is sent in clear text.

Just use your favourite packet sniffer to capture the DNS resolution, and seriously impact our web browsing privacy! Have a look at this plain text DNS query for the *kartapuce.com* domain. :mag:

{% include gallery id="gallery1" type="center" %}

Hopefully, our good [TLS](/protocols/tls) friend can help us! With **DNS over TLS (DoT)**, DNS traffic is wrapped within the TLS protocol, and TCP packets are sent fully encrypted over port 853. As another option, the **DNS over HTTPS (DoH)** protocol encapsulates DNS traffic within the HTTPS protocol over port 443. With these two options, the destination DNS server is authenticated, and DNS queries and answers are fully encrypted. :lock:

Let’s start by a capture of DoT queries to *kartapuce.com*.

{% include gallery id="gallery2" type="center" %}

We can now compare it with DoH queries!

{% include gallery id="gallery3" type="center" %}

DoT has **less latency** than DoH, and is much easier to filter for our beloved network administrators. :hearts: However, DoH provides even **more privacy** since DNS queries are hidden within the huge HTTPS traffic.
{: .notice--warning}

## DNSSEC

DoT and DoH achieve **DNS server authentication**. However, due to the recursive approach of DNS and to the numerous DNS caching servers, the DNS records are often not directly provided by the authoritative DNS servers. It would be fantastic to be able to directly **authenticate the DNS records**! It is possible with **Domain Name System Security Extensions (DNSSEC)**. :trophy: DNSSEC is still not largely adopted. It is a complex process that requires extensive knowledge for its initial setup and ongoing configuration. It is recommended to perform a risk analysis before rushing headlong into DNSSEC. :fast_forward:

DNSSEC provides protection against **DNS cache poisoning**. :boom: However, if an attacker has breached a DNS domain and is able to sign a DNS record, that is yet another issue!
{: .notice--warning}

Let’s establish a **chain of trust** with DNSSEC!

{% include gallery id="gallery4" type="center" %}

<div class="notice--warning" markdown="1">
Watch out cyber nerds, the [Root Signing Ceremony](https://www.iana.org/dnssec/ceremonies) is about to begin. What’s going to happen today: new ZSK, new hardware? :grinning:

**Note:** The *dig* and *devl* commands will be your most valuable friends to understand the fabulous world of DNS queries. Have a look at the following commands!
- *dig @8.8.8.8 domain +dnssec*
- *delv @8.8.8.8 domain +dnssec +vtrace*
</div>

**Note:** Based on original learning from [Cloudflare](https://www.cloudflare.com) engineers.
{: .notice--info}
