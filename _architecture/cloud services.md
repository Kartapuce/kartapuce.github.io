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
- **Containers as a Service** (CaaS): Build containers images. Orchestrate and manage instances. *Will you scale that container for me ?* :whale:
- **Platform as a Service** (PaaS): Provision of a full development environment. *What do you want to build today?*
- **Function as a Service** (FaaS): Event-based execution of stateless code. *If that, run that. And that.* 
- **Software as a Service** (SaaS): Delivery of everything required for running a software. This is the most widely used service model. *Keep calm and pay the software licence.*

{% include gallery id="gallery1" type="center" %}

**Note:** As a general rule, the "**as a Service**" model encompasses any service that is provided by a second party. So that you can focus on the business, and abstract all the underlying complexity. And then marketing took it all. :heart: Backup as a Service (BaaS), Identity as a Service (IDaaS), Security as a Service (SECaaS), Desktop as a Service (Daas)... Pretty much anything you want. :see_no_evil:
{: .notice--warning}

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
- **Multi-cloud**: In order to avoid vendor lock-in, the customer decides to benefit from several CSP services. *I still want it all.* :stuck_out_tongue_winking_eye:

{% include gallery id="gallery3" type="center" %}

**Note:** Most of the time, a company have a multi-cloud strategy due to regulation constraints, or successive acquisitions of companies. Multi-cloud increases the governance complexity, but it can also be leveraged in order to obtain competitive prices. :pray:
{: .notice--warning}

## Risk and opportunities

Moving to the cloud is not an end in itself, and it is not a binary decision. The strategy shall only be based on the business value expected from cloud services:
- **Flexibility**: the infrastructure is provided rapidly. It has *hyperscale* features, which permit to scale rapidly for short-term needs, or traffic bursts. :chart_with_upwards_trend:
- **Resiliency**: better tolerance to unexpected disruptions of service (due to attacks or failures) in order to ensure business continuity.
- **Simplicity**: part of the installation, administration, and security of the infrastructure can be delegated to competent CSPs. But we still face the cloud experts shortage.:computer:
- **New services**: CSPs provide a lot of services that could create business value: analytics, machine learning... But stay focus on the expected output from  all these tools.

But any strategy that is solely based on the following indicators will fail:
- **Cost**: the bill is more predictable without fixed entry fees, and matches business needs with pay-as-you-go pricing. But nothing prevents a CSP from increasing the pricing. :moneybag: And some services may be cheaper with on-premise datacenters.
- **Delegation of responsibility**: the use of cloud services creates a shared responsiblity, which might be tricky to understand depending on the service model. The CSP may be responsible for the security *of the cloud*, but the customers remain accountable for anything that happens *within the cloud*.

**Note:** Moving to the cloud requires to adopt a new *cloud mindset* in order to benefit from its capacities. A generalized *lift and shift* approach would probably fail. Migrating to *cloud-native* applications, rethinking the governance, updating the risk-analysis, rewriting the playbooks.. It requires a lot of time and expertise. :coffee:
{: .notice--warning}

## Security breaches

This model highlights some AWS services along with security breach examples.

{% include gallery id="gallery4" type="center" %}

<div class="notice--warning" markdown="1">
**Note:** A few punchlines to conclude :boom:  
- *There is no cloud, it’s just someone else’s computer.* :loudspeaker: Yes, but cloud service is also the flexibility to select the CSP nationality and legislation, the deployment model, the sensitivity of shared data and applications…  
- *Easy to get in, hard to get out.* That's probably the purpose of any CSP. :dollar: But some service models such as CaaS may reduce the stickyness to the CSP.  
- *Keep the technical debt. Pay the interest.* Migrating a technical debt to the cloud won't solve any problem. But it may make it even more costly.  
- *Your data is my data. :us:* The **FISA 702** and the extraterritoriality of the **Cloud Act**, adopted by the United States Congress, raise major issues for data privacy, and are not compatible with data sovereignty. And all the CSP leaders are in the target: Amazon Web Services, Microsoft Azure, Google Cloud Platform, Oracle Cloud...
</div>

**Note:** Based on original learning material from [OVHcloud](https://www.ovhcloud.com/) engineers.
{: .notice--info}
