---
layout: single
author_profile: false
title: "Virtualization"
excerpt: "Overview of virtualization technologies over the ages."
sidebar:
  nav: "architecture"
header:
  teaser: /assets/images/virtualization/vxlan.png
gallery1:
  - url: /assets/images/virtualization/nic.png
    image_path: assets/images/virtualization/nic.png
gallery2:
  - url: /assets/images/virtualization/lag.png
    image_path: assets/images/virtualization/lag.png
gallery3:
  - url: /assets/images/virtualization/mc lag.png
    image_path: assets/images/virtualization/mc lag.png
gallery4:
  - url: /assets/images/virtualization/ip alias.png
    image_path: assets/images/virtualization/ip alias.png
gallery5:
  - url: /assets/images/virtualization/vlan.png
    image_path: assets/images/virtualization/vlan.png
gallery6:
  - url: /assets/images/virtualization/vxlan.png
    image_path: assets/images/virtualization/vxlan.png
gallery7:
  - url: /assets/images/virtualization/vrrp.png
    image_path: assets/images/virtualization/vrrp.png
gallery8:
  - url: /assets/images/virtualization/glbp.png
    image_path: assets/images/virtualization/glbp.png
gallery9:
  - url: /assets/images/virtualization/vrf.png
    image_path: assets/images/virtualization/vrf.png
gallery10:
  - url: /assets/images/virtualization/virtual switching.png
    image_path: assets/images/virtualization/virtual switching.png
gallery11:
  - url: /assets/images/virtualization/server virtualization.png
    image_path: assets/images/virtualization/server virtualization.png
gallery12:
  - url: /assets/images/virtualization/storage virtualization.png
    image_path: assets/images/virtualization/storage virtualization.png
---

The use of virtualization in network and compute components is not something new. These protocols provide example of virtualization technologies that have been existing for decades. :hourglass:

## NIC teaming / trunking / bundling / bonding / channeling

Create a single logical bonded interface out of 2 or more NIC slaves. Especially used in the context of LAG.

{% include gallery id="gallery1" type="center" %}

## Link Aggregation Group (LAG)

Aggregation of multiple network connections in order to provide higher throughput and provide redundancy.
- Round robin: transmit alternate packets in sequential order from first slave to last slave
- Active-backup: a different backup slave becomes active only if the active slave fails
- XOR: selection of the slave based on MAC address / IP address / Port number
- Broadcast: transmit on all the slaves

{% include gallery id="gallery2" type="center" %}

## Multi Chassis Link Aggregation Group (MLAG MC-LAG)

Type of LAG where ports terminate on separate chassis in order to improve redundancy in the event one of the chassis fails.

{% include gallery id="gallery3" type="center" %}

## IP aliasing

Use of one single physical interface with several virtual IP adresses.

{% include gallery id="gallery4" type="center" %}

## Virtual Local Area Network (VLAN)

Creation of several broadcast domains within one single physical switch. Even though it is basically not a security features, it also provides virtual segmentation of a network.

{% include gallery id="gallery5" type="center" %}

## Virtual Extensible Local Area Network (VXLAN)

VLAN like encapsulation of Layer 2 ethernet frames within Layer 4 UDP datagrams. VLANs can now be routed at Layer 3 level between Virtual Tunnel Endpoints (VTEPs).

{% include gallery id="gallery6" type="center" %}

## Virtual Router Redundancy Protocol (VRRP) / Hot Standby Router Protocol (HSRP)

Grouping of several routers behind one single MAC adress and IP adress in order to increase the availability of the gateway in case of failure of the master router.

{% include gallery id="gallery7" type="center" %}

## Gateway Load Balancing Protocol (GLBP)

Provides the same benefits as VRRP for high availability, but increases the performance thanks to load-balancing features.

{% include gallery id="gallery8" type="center" %}

## Virtual Routing and Forwarding (VRF)

Creates multiple virtual routers (each with their own separate routing table, independent routing protocols…) from a single physical appliance.

{% include gallery id="gallery9" type="center" %}

## Virtual switching

An hypervisor emulates a switch in order to control the traffic between virtual machines.

{% include gallery id="gallery10" type="center" %}

## Server virtualization

One single hypervisor hosts several virtual machines (guest operating systems), achieving similar performances to having the applications running on separate hardware instances. It also provides the abstraction of the underlying hardware (CPU, RAM…). It got enhanced with features such as high availability, vMotion, automatic scalabilty, fault tolerance...

{% include gallery id="gallery11" type="center" %}

## Storage virtualization

With Redundant Array of Independent Disks (RAID), multiple hard disk drives are aggregated in order to achieve better read / write performance, or higher availability.

{% include gallery id="gallery12" type="center" %}

**Note:** Based on original learning material from [VMWare](https://www.vmware.com/learning) documentation *VMWare NSX Network Virtualization Fundamentals*.
{: .notice--info}
