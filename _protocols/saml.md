---
layout: single
author_profile: false
title: "SAML 2.0"
excerpt: "Federated identities with Security Assertion Markup Language."
sidebar:
  nav: "protocols"
header:
  teaser: /assets/images/SAML-small.png
gallery1:
  - url: /assets/images/SAML.png
    image_path: assets/images/SAML.png
---
## Introduction

SAML 2.0 is a standardized way to authenticate a user across multiple applications, using the concept of federated identities.
It includes the followings stakeholders:
- **The subject** wants to authenticate only once across several applications. It can be a human or a non-human entity such as a software or a server.
- **The federated applications** rely on the Identity Provider for users authentication. They can be hosted by a CSP or internally.
- **The Identity provider** stores and manages users’ digital identities and authorizations. It is often merged with the **SSO server**, which provides a unified place for users to sign in to all the federated applications. If the services responsible for IAM are cloud-hosted as SaaS, they are refered to as *Identity-as-a-service (IDaaS)*.

## Use Case

Every day at work, Alice needs to authenticate on Salesforce, Sharepoint and Tableau to do her job. In order to avoid to authenticate on each on these platforms, she authenticates only once on a unified portal. Her Admin Sys is also happy since it becomes much more efficient to apply internal security policies.

## SAML 2.0

Let's federate all this ! :stuck_out_tongue_winking_eye:

{% include gallery id="gallery1" type="center" %}

**Note:** Based on original learning material from [Cloudflare](https://cloudflare.com/learning) engineers.
{: .notice--info}
