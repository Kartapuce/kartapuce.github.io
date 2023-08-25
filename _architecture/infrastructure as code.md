---
layout: single
author_profile: false
title: "Infrastructure as Code"
excerpt: "Let's automate these tasks!"
sidebar:
  nav: "architecture"
header:
  teaser: /assets/images/ansible/ansible-small.png
gallery1:
  - url: /assets/images/ansible/ansible.png
    image_path: assets/images/ansible/ansible.png
gallery2: 
  - url: /assets/images/ansible/playbooks.png
    image_path: assets/images/ansible/playbooks.png
---

## IT automation

Let’s have a deep dive into the marvellous world of **IT automation**! :heart_eyes:

The Kartapuce IT infrastructure is made of al lot of **hardware and software resources for compute, network and storage**.  :minidisc: Back in the old days, it consisted of physical devices installed on-premise. So any time we wanted to set up a new bunch of servers, we had to go through the procurement, then the field engineers, system / network / security / storage administrators, before finally delivering the devices to the application team. A very long and error-prone process, with a lot of repeated and manual actions! :no_good: As the infrastructure moved to private and public clouds, CSP started to provide a set of APIs that allowed customers to automate the provisioning of their infrastructure.

## Infrastructure as Code

Thanks to **Infrastructure as Code (IaC)**, all the provisioning and management of the IT infrastructure is achieved through code in stead of manual processes. :books: By setting up all these resources in configuration files, the infrastructure is easier to edit, version, and distribute, and it provides a modular approach using reusable building blocks. Kartapuce realized very soon that writing its own deployments scripts required a lot of coding skills, but the shift to dedicated IaC tools permitted to gain velocity and money, by natively supporting a lot of CSP providers and IT products manufacturers. No more configuration drift due to unmanaged operations on the IT! :pray:

Basically, the IaC tools can be divided into 3 main categories:
- **Infrastructure Provisioning**: the process of creating and provisioning the native immutable IT infrastructure. It is achieved with tools such as Terraform or CloudFormation.
- **Configuration Management**: the process of defining and maintaining a consistent mutable configuration across the IT infrastructure. :clipboard: It is achieved with tools such as Ansible, Chef, or Puppet.
- **Server Templating**: the process of creating immutable images for our VMs and Containers, that can easily be distributed and deployed. :whale: It is achieved with tools such as [Docker](/architecture/containers) and Packer, and is enhanced by orchestration tools such as Kubernetes and Docker Swarm.

## Ansible for Configuration Management

Let’s start with **Ansible**, an IT automation tool that primarily focuses on the Configuration Management process.

The Ansible architecture relies on a Control Node and several Managed Nodes under its control.

{% include gallery id="gallery1" type="center" %}

Our system administrator here at Kartapuce, John, never deploys any configuration host by host anymore. :zzz: Instead, John uses Ansible ad-hoc commands to natively perform on several hosts the tasks that are rarely repeated. But above all, John relies on Ansible playbooks written in YAML format to configure the IT systems. :sunglasses: Playbooks use a **procedural (declarative) approach** to describe step-by-step the list of instructions that need to be achieved. Since Ansible is **idempotent**, executing a playbook several times won’t create any inconsistency: Ansible discards the tasks already achieved, and only performs the tasks that permit to reach the intended state.

{% include gallery id="gallery2" type="center" %}

John relies a lot on the roles and collections provided by partners on the **Ansible Galaxy**. For automating security, he uses the firewalld module to set up firewall rules, the CyberArk modules for its PAM, CrowdStrike module for EDR… John got rid of repetitive tasks, John is happy. :tada:

Ansible manipulates a lot of sensitive data such as passwords and keys. These data shall obviously not be hardcoded in playbooks or roles, or stored in plaintext on the Control node. :bell: Ansible comes with **Ansible Vault**, that protects data at rest by encrypting sensitive variables and files. Ansible can also retrieve data form external secrets management tools, such as Hashicorp Vault.

<div class="notice--warning" markdown="1">
**Ansible commands 101:**
- *Using the ping module:* ansible webservers -m ping -i inventory.txt
- *Using the default command module with reboot parameter:* ansible webservers -a “/sbin/reboot” -i inventory.txt
- ansible-playbook -i inventory.txt kartapuce-playbook.yaml
</div>

**Note:** Based on original learning material from [Ansible](https://docs.ansible.com/) engineers.
{: .notice--info}
