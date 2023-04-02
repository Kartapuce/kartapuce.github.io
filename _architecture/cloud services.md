---
layout: single
author_profile: false
title: "Cloud services"
excerpt: "Shedding light on a cloudy topic."
sidebar:
  nav: "architecture"
header:
  teaser: /assets/images/cloud/vulnerabilities-small.png
gallery1:
  - url: /assets/images/cloud/service.png
    image_path: assets/images/cloud/service.png
gallery2:
  - url: /assets/images/cloud/sharing.png
    image_path: assets/images/cloud/sharing.png
gallery3:
  - url: /assets/images/cloud/hosting.png
    image_path: assets/images/cloud/hosting.png
gallery4:
  - url: /assets/images/cloud/vulnerabilities.png
    image_path: assets/images/cloud/vulnerabilities.png
---

Let’s clarify some wording commonly used by **Cloud Service Providers** (CSP). Properly understanding the available services and the deployment models are essential to identify the risks and opportunities associated with this technology. :cloud:

## Service models

Let’s start with available services. In all cases, it all comes down to offering on-demand resources. But depending on the model, these resources can be hardware, software, or even a full development environment:
- **Infrastructure as a Service** (IaaS): Provision of hardware resources. *I’ve got all the CPU that you need.*
- **Platform as a Service** (PaaS): Provision of a full development environment. *What do you want to build today?* :wrench:
- **Software as a Service** (SaaS): Delivery of everything required for running a software. This is the most widely used service model. *Keep calm and pay the software licence.*

{% include gallery id="gallery1" type="center" %}

## Deployment models

Now let’s review deployment models.

### Sharing strategy

The first aspect concerns the sharing strategy. In order to provide scalable resources, CSPs may mutualize resources for several customers. In any case, the CSP remains accountable for ensuring proper isolation between customers.
- **Public cloud**: Shared resources for all customers, in order to benefit from mutualized infrastructure. *I don’t know you, but let’s mutualize that power.* :boom:
- **Private cloud**: Resources dedicated to one single customer, for exclusive control over the infrastructure. *I will never share my toys with you.*
- **Community cloud**: Shared resources for selected members with the same standards. *Sorry, that’s a select club here.* :bowtie:
- **Hybrid cloud**: A mix of public, private, and community cloud, depending on the sensitivity of the data. *I want it all.*

{% include gallery id="gallery2" type="center" %}

### Hosting strategy

The second aspect concerns the hosting strategy.
- **On-premise datacentre**: Hosting your own datacentre without cloud services. *Sorry, not interested in your cloudy business.* :european_castle:
- **On-premise private cloud**: Private cloud directly hosted within the customer facility. *I want to keep it home.*
- **Hosted cloud**: The most common hosting strategy, where services are directly hosted by the CSP. *I’ll just handle it remotely.*
- **Multi-cloud**: In order to avoid vendor lock-in, the customer decides to benefit from several CSP services. *I still want it all.*

{% include gallery id="gallery3" type="center" %}

## Risk and opportunities

Moving to the cloud is not always the best strategy. But customers may benefit from several advantages such as:
- Flexibility: the infrastructure is provided rapidly. It is reliable and scalable depending on business needs.
- Simplicity: the installation, administration, security of the infrastructure can be delegated to competent CSPs in order to focus on creating business value.
- Cost: the bill is more predictable without fixed entry fees, and matches business needs with pay-as-you-go pricing. But nothing prevents a CSP from increasing the pricing. :moneybag:

This model highlights some AWS services along with security breach examples.

**(Reductive) punchline:** *There is no cloud, it’s just someone else’s computer.* :loudspeaker: Yes, but cloud service is also the flexibility to select the CSP nationality and legislation, the deployment model, the sensitivity of shared data and applications…
{: .notice--warning}

{% include gallery id="gallery4" type="center" %}

**Note:** Based on original learning material from [OVHcloud](https://www.ovhcloud.com/) engineers.
{: .notice--info}
