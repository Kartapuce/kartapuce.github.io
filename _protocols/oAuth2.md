---
layout: single
author_profile: false
title: "OAuth 2.0"
excerpt: "Delegated identities with Open Authorization 2.0."
sidebar:
  nav: "protocols"
header:
  teaser: /assets/images/OAuth-small.png
gallery1:
  - url: /assets/images/OAuth.png
    image_path: assets/images/OAuth.png
---
## Introduction

OAuth 2.0 is a standardized way to authorize an application to request access to another application on behalf of its owner, using the concept of delegated identities.
However, OAuth 2.0 is not designed to authenticate on the client application!

## Use Case

Alice loves running, and she monitors her trainings with her Garmin watch. Alice wants to upload her trainings on from her Garmin account to her Strava account, so that her friends get motivation from her hard work! She wants to delegate to Garmin the privilege to upload her training on Strava.

In this example, the Strava authentication page itself performs the authorization. But for other uses cases, an authorization server such as Google Identity could handle this responsibility.

## OAuth 2.0

Let's see how the magic happens with OAuth 2.0 protocol. Make sure to properly follow the timeline!
For each data exchange, queries are in blue, and answer are in green.

{% include gallery id="gallery1" type="center" %}

**Note:** Pseudo-Authentication is a twisted use-case of OAuth 2.0 for authentication. The client (Garmin) authenticates a User (Alice) by obtaining the authorization to retrieve some dumb info (such as Alice name on Facebook) from the resource server (Facebook). If it is successful, the Client considers that the User properly authenticated on the Authorization server (Facebook Identity), and allows access to the application. This is not considered secure. Pseudo-Authentication is a twisted use-case of OAuth for authentication. [OpenID Connect](/protocols/openID connect) is a good alternative for combining authentication and delegated identities.
{: .notice--warning}

**Note:** Based on original learning material from [Auth0](https://auth0.com/docs) engineers.
{: .notice--info}
