---
layout: single
author_profile: false
title: "SOP and CORS"
excerpt: "Not going to let you read this!"
sidebar:
  nav: "protocols"
header:
  teaser: /assets/images/sop cors/SOP and CORS-small.png
gallery1:
  - url: /assets/images/sop cors/SOP and CORS.png
    image_path: assets/images/sop cors/SOP and CORS.png
---

## SOP and CORS

The **Same-Origin Policy (SOP)** restricts how a document or script loaded by one origin can interact with a resource from another origin.

Let’s consider a malicious website that would deliver a malicious JavaScript. Without SOP, this malicious JavaScript could query the Kartapuce bank account of a victim and retrieve the HTTP answer with the account balance, without exploiting any vulnerability! :dollar: As another example, this website could include an iframe from Facebook or LinkedIn, and directly retrieve the authentication [cookie](/protocols/cookies) of the user, without exploiting any vulnerability.

**Cross Origin Resource Sharing (CORS)** alleviates the constraints of SOP. A server can indicate which origins are allowed to read its resources. :pray: The request can be of type « simple request », or « preflighted request » to determine if the request is actually safe to send.

{% include gallery id="gallery1" type="center" %}

**Note:** Based on original learning material from [Mozilla](https://developer.mozilla.org/) engineers.
{: .notice--info}
