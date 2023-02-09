---
layout: single
author_profile: false
title: "OpenID Connect"
excerpt: "The magic of OpenID Connect."
sidebar:
  nav: "protocols"
header:
  teaser: /assets/images/OpenID Connect.png
gallery1:
  - url: /assets/images/OpenID Connect.png
    image_path: assets/images/OpenID Connect.png
---
## Introduction

In order to simplify the access to data, information systems tend to:
- centralize the authentication of users in Identity Providers (such as Facebook Connect),
- facilitate exchanges of data between applications.

OpenID Connect adds an authentication layer on top of [OAuth2.0](/protocols/oAuth2), and normalize the way to obtain basic information about the user.

## Use Case

Alicia loves running, and she wants to upload her trainings on her Strava account. Since she is fed up with multiple accounts, she wants to centralize the authentication with Facebook Connect. Of course, Alicia does not agree to provide her Facebook password to Strava.

Alicia does not want to manually input her birth date and address within Strava. So she wants to authorize Strava to directly retrieve this information from her Facebook account. If she moves to another address, she will only have to update her new address once in Facebook.

Since Alicia is also looking for the recognition of her friends, she wants to make sure that all her trainings are directly relayed by Strava to her Twitter account. Therefore, Alicia wants to delegate to Strava the authorization to publish on her Twitter account on her behalf.

Feel free to translate this mechanism to any use case that makes sense to you!

## OpenID Connect

Let's see how the magic happens with OpenID Connect protocol. Make sure to properly follow the timeline!
For each data exchange, queries are in black, and answer are in red.

{% include gallery id="gallery1" type="center" %}

**Note:** Based on original learning material from [ANSSI](https://www.ssi.gouv.fr) documentation *Recommandations pour la sécurisation de la mise en oeuvre du protocole OpenID Connect*.
{: .notice--info}
