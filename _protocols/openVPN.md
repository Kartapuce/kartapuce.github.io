---
layout: single
author_profile: false
title: "OpenVPN"
excerpt: "Check out OpenVPN configurations."
sidebar:
  nav: "protocols"
header:
  teaser: /assets/images/openVPN/NtoN routing physical.png
toc: true
toc_label: "openVPN"
toc_icon: "cog"
gallery1:
  - url: /assets/images/openVPN/Layers.png
    image_path: assets/images/openVPN/Layers.png
gallery2:
  - url: /assets/images/openVPN/NtoN routing physical.png
    image_path: assets/images/openVPN/NtoN routing physical.png
gallery3:
  - url: /assets/images/openVPN/NtoN routing logical.png
    image_path: assets/images/openVPN/NtoN routing logical.png
gallery4:
  - url: /assets/images/openVPN/HtoN routing physical.png
    image_path: assets/images/openVPN/HtoN routing physical.png
gallery5:
  - url: /assets/images/openVPN/HtoN routing logical.png
    image_path: assets/images/openVPN/HtoN routing logical.png
gallery6:
  - url: /assets/images/openVPN/HtoH routing physical.png
    image_path: assets/images/openVPN/HtoH routing physical.png
gallery7:
  - url: /assets/images/openVPN/HtoH routing logical.png
    image_path: assets/images/openVPN/HtoH routing logical.png
gallery8:
  - url: /assets/images/openVPN/HtoN bridging physical.png
    image_path: assets/images/openVPN/HtoN bridging physical.png
gallery9:
  - url: /assets/images/openVPN/HtoN bridging logical.png
    image_path: assets/images/openVPN/HtoN bridging logical.png 
---
## Introduction

When we **carry data over an unsecure network**, we want to make sure that:
- the data is not altered (on purpose or not),
- the data cannot be read by a third party.

Using a **Virtual Private Network (VPN)** ensures integrity and confidentiality of the data, as well as client / server mutual authentication. A VPN can be set up in order to secure:
- Network-to-network communications (between main branch and remote office),
- Host-to-network communications (remote user access),
- Host-to-host communications (private chat).

There are **two main categories of VPN: TLS VPN and IPsec with ESP VPN**.

**OpenVPN** is an open-source non standardized VPN (not described in any RFC) based on TLS encryption (for authentication and key exchange). It runs in user-land, and works over UDP on port 1194 (or TCP additionally). Therefore the opnVPN tunnel is set up above layer 4. It **encapsulates the encrypted packet within an IP/UDP segment**, which makes it hard to detect. It can transport **layer 2 Ethernet frames or layer 3 IP datagrams**. Additionally to the use of the client certificate, it is possible to ask the client to provide a username and password, and to pass it to the OpenVPN gateway over the secure TLS channel. By default, OpenVPN clients cannot talk one to another.

{% include gallery id="gallery1" type="center" %}

## Routing mode: tunnels L3 IP datagrams

When the client machines connect via **routing mode, they use their own separate subnet**, and routes are set up on both the client machines and remote remote gateway so that data will seamlessly traverse the VPN.
- Transports only layer 3 IP datagrams (IPv4 and IPv6),
- The LAN and the VPN clients do not belong to the same broadcast domain (broadcast traffic is not transported),
- The **TUN device** is a virtual point-to-point IP link (allow IP forwarding on the OpenVPN gateway).

### Network-to-network routing mode

#### Physical modelling

{% include gallery id="gallery2" type="center" %}

#### Logical modelling

{% include gallery id="gallery3" type="center" %}

### Host-to-network routing mode

#### Physical modelling

{% include gallery id="gallery4" type="center" %}

#### Logical modelling

{% include gallery id="gallery5" type="center" %}

### Host-to-host routing mode

#### Physical modelling

{% include gallery id="gallery6" type="center" %}

#### Logical modelling

{% include gallery id="gallery7" type="center" %}

## Bridging mode: tunnels layer 2 Ethernet frames

When the client machine connects via bridging mode, **they are assigned an IP address that is part of the remote physical ethernet subnet**, and are then able to interact with other machines on the remote subnet as if they were connected locally.
- Transports any network protocol (IPv4 as in the example, Netalk, IPX...). Ethernet frames are passed over the VPN tunnel (useful for running applications which rely on network broadcasts such as LAN games),
- The LAN and the VPN clients belong to the same broadcast domain (e.g. required for getting an IP address from a DHCP server on the LAN),
- The **TAP device** is a virtual ethernet adapter (promiscuous mode on the OpenVPN gateway).

### Host-to-network bridging mode

#### Physical modelling

{% include gallery id="gallery8" type="center" %}

#### Logical modelling

{% include gallery id="gallery9" type="center" %}

**Note:** Based on original learning material from [OpenVPN](https://openvpn.net//) documentation.
{: .notice--info}
