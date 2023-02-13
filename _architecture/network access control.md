---
layout: single
author_profile: false
title: "Network access control"
excerpt: "Control network users with 802.1X."
sidebar:
  nav: "architecture"
header:
  teaser: /assets/images/Network Access Control-small.png
gallery1:
  - url: /assets/images/Network Access Control.png
    image_path: assets/images/Network Access Control.png
---

Let’s consider an IT environment where the access to internal resources is based on the physical location of the user. If an attacker manages to physically connect to an internal network equipment, he gets access to sensitive information. As part of the **defense-in-depth** architecture pattern, it is recommended to strictly restrict network access to explicitly authorized users only. The **802.1X** protocol enforces such **Network Access Control (NAC)**.

## Main components and protocols

The components involved in network access control are:
- the **AAA server**: responsible for Authentication and Authorization of the supplicants and Accounting of exchanges. It controls the state of clients ports between « closed port » (only allowing EAP exchanges) and « open port » (allowing any traffic).
- the **client**: network equipment providing network access to the interna network. It can be a switch, a WiFi access point… By default, its ports are in the « closed port » state. It is also referred to as the authenticator.
- the **supplicant**: the user who wants to be part of the internal network. The supplicant may perform automatic authentication, or require an action from the user.

The authentication between the supplicants and the server relies on the **Extensible Authentication Protocol (EAP)**. Several methods of this protocol exist. The recommended methods are:
- EAP-TLS: the client and the server authenticate with their private key and certificate. A PKI is therefore required.
- EAP-PEAP: the server authenticates with a certificate, then the user can authenticate with a login / password within a TLS tunnel.

The EAP exchange is encapsulated within the **EAPoL** protocol between the supplicants and the client (wired or wireless), and within the **Radius** protocol between the client and the server.

**Note:** MAC authentication based on the MAC address of the client is not secure and shall never be used as a standalone method to enforce network access control. It is really easy to change a MAC address in order to impersonate an authorized user.
{: .notice--warning}

## Architecture

This model highlights some vulnerabilities associated with network access control, and how to thwart them with 802.1X.

**Note:**  Setting up advanced secure features such as static VLANs per port, or listing of authorized MAC, always comes at the expense of flexibility. Like always in security, a trade-off needs to be performed between hardening and agility based on a risk analysis.
{: .notice--warning}

{% include gallery id="gallery1" type="center" %}

**Note:** Based on original learning material from [ANSSI](https://www.ssi.gouv.fr/) documentation *Recommandations de déploiement du protocole 802.1X pour le contrôle d'accès à des réseaux locaux*.
{: .notice--info}
