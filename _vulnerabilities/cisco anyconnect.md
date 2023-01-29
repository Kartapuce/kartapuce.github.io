---
layout: single
author_profile: false
title: "CVE-2020-3153 Cisco AnyConnect"
excerpt: "Focus on CVE-2020-3153"
sidebar:
  nav: "vulnerabilities"
header:
  teaser: /assets/images/CVE-2020-3153 Cisco Anyconnect.png
gallery1:
  - url: /assets/images/CVE-2020-3153 Cisco Anyconnect.png
    image_path: assets/images/CVE-2020-3153 Cisco Anyconnect.png
---

This modelling illustrates how the combination of several vulnerabilities on Cisco AnyConnect allows a low-priv attacker to obtain an admin command prompt.

## Some backgroung about Cisco AnyConnect

Cisco AnyConnect contains several executables and dll files, which exchange data through IPC (Inter-Process Communication) on TCP interface 127.0.0.1:62522:
- vpnagent.exe executed as LocalSystem (with NT AUTHORITY\SYSTEM token)
- vpnui.exe executed as unprivileged current user (kartapuce)
- vpndownloader.exe
- anyconnect.exe

<div class="notice--success" markdown="1">
**Quick reminder:** Executables and DLL:
- « .exe » : **Executable files** create a new process when executed,
- « .dll » : **Dynamic Link Library files** are called by an executable in order to provide re-usable classes and methods.
</div>

Traffic analysis permits to obtain the structure of Cisco AnyConnect IPC messages .The structure is : Type (2 bytes) – Longueur (2 bytes) – Value (variable). It is now possible to parse the binary content, and to read the field values (ASCII encoding).

<div class="notice--success" markdown="1">
**Useful analysis tools:**
- Analysis of messages over the network (including IPC) with Wireshark
- Analysis of Windows activities (processus, registres…) with  Windows Sysinternals Process Monitor
- Analysis of applicative events in Windows event logs.
</div>

## CVE-2020-3153

This modellings details the timeline of the attack.

{% include gallery id="gallery1" type="center" %}


**Note:** Based on original learning material from [MISC](https://connect.ed-diamond.com/misc) documentation *MISC 112 - CVE-2020-3433 : élévation de privilèges sur le client VPN Cisco AnyConnect*.
{: .notice--info}
