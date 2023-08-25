---
layout: single
author_profile: false
title: "Identity and Access Management"
excerpt: "Knock, knock! Who's there?"
sidebar:
  nav: "architecture"
header:
  teaser: /assets/images/iam/customers-small.png
gallery1:
  - url: /assets/images/iam/customers.png
    image_path: assets/images/iam/customers.png
gallery2: 
  - url: /assets/images/iam/global iam.png
    image_path: assets/images/iam/global iam.png
---

## What is IAM about?

**Identity and Access Management** is the process of managing digital identities and access to the resources. In a few words, make sure that “*The right individuals access the right resources at the right time for the right reasons*”. :cop:

This process involves the following steps:
- **Identification**: An entity (human or non-human) claims to be somebody. :loudspeaker:
- **Authentication**: The entity proves that it is who it claims to be. :key:
- **Authorization**: Once the subject is authenticated, a Policy Decision Point determines what is allowed. It uses its identity and permissions (roles), and can also use contextually specific access criteria such as the time, the localisation… :mag_right:
- **Access Control**: Once the authorizations are retrieved, a Policy Enforcement Point actually allows or reject the request to access a resource.

**Note:** Identities need to be managed during their whole **lifecycle**, from the initial mapping of a claimed identity with a real-life existence of a subject during account creation, up to its modification and destruction.
{: .notice--warning}

## Evolution of IAM :cloud:

- At the very beginning, IAM mostly concerned **on-premise monolithic applications** which had their own authentication mechanisms. Authorization was granted based on access control lists specifying the allowed subjects for each resource. :orange_book: The resource owner used to grant access to other subjects (*Discretionary Access Control – DAC*).
- Then, the LDAP and Kerberos protocols were deployed in order to **centralize the IAM process**. The Microsoft Active Directory service thrived, and permitted to handle all the users and assets within an on-premise Windows domain. Instead of individual subject identities, the access to resources started to be based on roles assigned to the users (*Role-Based Access Control – RBAC*).
- As companies started to migrate to the cloud, many resources were externalized outside of the perimeter of the organization. Instead on using an on-premise solution, several companies adopted **Identity as a Service (IDaaS)** solutions, and delegated to a third-party the responsibility to build and operate the IAM service. With more users outside of the enterprise boundaries, coupled with Zero Trust adoption, the **continuous authentication and authorization** paradigm started to take into account the localisation, the time, the type of operation… (*Attribute-Based Access Control - ABAC*). :earth_americas: This was reinforced with external data from the CTI or detection tools, sensitivity of the asset… to compute a risk level for each IAM operation (*Risk-Based Access Control* with the 5 Ws). :sunglasses:

## Identity federation, Identity federation everywhere…

That’s definitely a new key concept. **Identity Federation** is the process of asserting an identity across different systems or organizations. With the surge of multi-cloud and SaaS applications, it is now a paramount topic for companies! It requires to build a trust relationship between an organization and the identity provider which is accountable for verifying user identity, using protocols such as [SAML](/protocols/saml) and [OpenID Connect](/protocols/openID connect).

Let’s illustrate this with the example of Alice, who is a customer of Kartapuce services. :woman: She definitely does not want to create a new profile for all her sport applications. Alice much prefers to federate everything on her Google social profile!

{% include gallery id="gallery1" type="center" %}

## So many IAM systems!

For Kartapuce, building an IAM solution is not only about the customers! It is also necessary to handle the access for many users:
- Employees with B2E employees **Identity and Access Management (IAM)**
- Administrators and privileged accounts with **Privileged Access Management (PAM)** :crown:
- Customers (partners and consumers) with B2B and B2C **Customer Identity and Access Management (CIAM)** :hammer:

Let’s illustrate this with Kartapuce IAM architecture!

{% include gallery id="gallery2" type="center" %}

A lot of new features are provided by current IAM solutions:
- **Just-in-Time provisioning**: automate the creation of a user profile on an application during first login :boom:
- **SCIM (System for Cross-Domain Identity Management)**: automate the transfer of information between the identity provider and the applications, in order to keep synchronized data across apps, and to automate both onboarding and offboarding of users
- **Self-service registration**: allow customers to self-register on an application, reset their passwords… (with features such as email verification)
- **Progressive profiling**: incrementally collect profile data over time
- **Just-in-Time access**: avoid giving permanent elevated privileges, by giving real-time elevated privileges for sensitive operations
- **Adaptative MFA**: require MFA when detecting changes in authentication scheme
- **Attacks-detection**: increase detection of breached password, suspicious IPs, bots login… :bell:
- **Unified SSO**: SSO for on-premise and cloud-based applications
- **Device assurance**: ensure that devices meet some security requirements before authorizing access (managed devices, OS / web client versions…) :computer:

**Note:** Based on original learning material from [Okta](https://www.okta.com/) engineers.
{: .notice--info}
