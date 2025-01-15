---
layout: single
author_profile: false
title: "Secure administration of IT systems"
excerpt: "One network to rule them all."
sidebar:
  nav: "architecture"
header:
  teaser: /assets/images/Secure administration of IT systems-small.png
gallery1:
  - url: /assets/images/Secure administration of IT systems.png
    image_path: assets/images/Secure administration of IT systems.png
---

**Administration operations** aim at keeping an information system (IS) in **operating and secure condition**, and to **manage changes** to the IS. Therefore, administration actions include all the operations of installation, deletion, modification or consultation for the configuration of an IT system. :triangular_ruler:

Let’s consider the Kartapuce company. Administrators encompass a large variety of profiles:
- **technical administrators** are accountable for the administration of network equipment (routers, switches), compute resources (servers), storage resources (database, SAN), security products (firewall, EDR), end user resources (laptop, printers…)... both on-premise and in the cloud
- **functional administrators** are specifically involved in the administration of applications (including identity management, software integration).

Each administrator profile has its **own set of privilegies** granted on the IS. They execute administrative tasks with different tools depending on the context: **local tools** installed on their laptops (such as an SSH client or a thin client), or **centralized tools** that administrate resources, which may provide a full user interface (UI) in a web browser, or only a command-line interface (CLI). :pencil2:

Let’s highlight some recommendations for the secure administration of an IT system! This diagram mostly concerns traditional VPN-based IS, but still provides valuable insights for cloud-based environments. :cloud:

{% include gallery id="gallery1" type="center" %}

**Note:** Based on original learning material from [ANSSI](https://www.cyber.gouv.fr/) documentation *Recommandations relatives à l’administration sécurisée des systèmes d’information v3*.
{: .notice--info}
