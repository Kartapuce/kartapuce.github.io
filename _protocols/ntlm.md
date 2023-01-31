---
layout: single
author_profile: false
title: "NTLMv2 and Kerberos"
excerpt: "Authentication protocols within a Windows domain."
sidebar:
  nav: "protocols"
header:
  teaser: /assets/images/ntlm/kerberos.png
gallery1:
  - url: /assets/images/ntlm/interactive ntlm.png
    image_path: assets/images/ntlm/interactive ntlm.png
gallery2:
  - url: /assets/images/ntlm/network ntlm.png
    image_path: assets/images/ntlm/network ntlm.png
gallery3:
  - url: /assets/images/ntlm/kerberos.png
    image_path: assets/images/ntlm/kerberos.png
---
## Introduction

Authentication within a Windows domain relies on the **NTLM** or **Kerberos** protocols. NTLMv2 is deprecated, but it is still used as a backup when Kerberos fails.

<div class="notice--success" markdown="1">
**Note:** Active Directory is a solution developed by Microsoft for the management of an information system. It contains:
- a resource directory service (LDAP)
- an authentication scheme (Kerberos)
- a domain resolution service (DNS)
- a software policy
</div>

In this example, let's consider the user Alice who tries to authenticate ! We detail the authentication scheme for:
- **interactive logon:** the user provides inputs for authentication against a server or a Domain Controller.
- **network logon:** the authentication performed by the user as part of interactive logon is used again to log the user on another resource.

### Interactive logon with NTLM *(TBC)*

**Note:** I've never been so sure about the clear-text password for interactive logon.
{: .notice--warning}

{% include gallery id="gallery1" type="center" %}

### Network logon with NTLM

{% include gallery id="gallery2" type="center" %}

### Interactive and network logon with Kerberos

{% include gallery id="gallery3" type="center" %}

**Note:** Based on original learning material from [Microsoft](https://learn.microsoft.com) engineers.
{: .notice--info}
