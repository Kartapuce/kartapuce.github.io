---
layout: single
author_profile: false
title: "Secure SMTP infrastructure"
excerpt: "Everything you've always wanted to know about SMTP."
sidebar:
  nav: "architecture"
header:
  teaser: /assets/images/Secure SMTP infrastructure-small.png
gallery1:
  - url: /assets/images/Secure SMTP infrastructure.png
    image_path: assets/images/Secure SMTP infrastructure.png
---

## Architecture

This modelling aims at describing the different components that are part of a **Simple Mail Transfer Protocol (SMTP)** infrastructure, and their location within a secure gateway.

:x: It highlights several well-known attacks on an SMTP infrastructure:
- disclosure of confidential data,
- spoofing of identity,
- typosquatting / malware / phishing / DoS,
- disclosure or alteration of email content.

:heavy_check_mark: And it identifies the means to protect:
- SMTPS / IMAPS / STARTTLS,
- DKIM / SPF,
- attached-file analysis / SPAM detection / email quarantines / whitelisting,
- end-to-end integrity and confidentiality.

## Use Case

In this example, let's consider the user Bob. He is a valuable member of Kartapuce, and belongs to the kartapuce.com domain. Bob wants to send IOCs to his colleague Jack, and to his friend Tom on his personal email.

Let's have a look at all the operations that happen under the wood! :stuck_out_tongue:

{% include gallery id="gallery1" type="center" %}

**Disclaimer:** These are obviously not the real architecture and IP addresses for reaching to a friend on GMail!
{: .notice--warning}

**Note:** Based on original learning material from [ANSSI](https://www.ssi.gouv.fr/) documentation *Recommandations relatives à l’interconnexion d’un système d’information à Internet*.
{: .notice--info}
