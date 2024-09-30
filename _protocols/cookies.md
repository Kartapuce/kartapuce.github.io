---
layout: single
author_profile: false
title: "Cookies"
excerpt: "Not about bakery."
sidebar:
  nav: "protocols"
header:
  teaser: /assets/images/cookies/third party cookies-small.png
gallery1:
  - url: /assets/images/cookies/first party cookies.png
    image_path: assets/images/cookies/first party cookies.png
gallery2: 
  - url: /assets/images/cookies/third party cookies.png
    image_path: assets/images/cookies/third party cookies.png
---

## First-party cookies

**Cookies** are small files sent from a website to a user’s web browser. :cookie: They are often used to provide a personalized experience to the user. :wave:

When a browser sends an HTTP request to a domain, any cookies, including authentication session cookies, relevant to the domain are typically sent as part of the request. Sometimes it must be forced explicitly for cross-site requests. The website that issues the cookies can explicitly set some attributes to **reinforce security**:
- **HttpOnly**: The cookie can’t be accessed or modified with JavaScript (with Documet.cookie for example). It comes with the requirement that only the backend application needs them. This attribute helps to mitigate XSS attacks.
- **Secure**: The cookie is only sent to the server through an encrypted request (HTTPS protocol).
- **SameSite**: The server specifies whether cookies are sent with cross-site requests (strict, lax, none). It helps to mitigate **CSRF Attacks**. Default is « lax »: cookies are sent in the request only if the user is navigating to the origin site from an external site (by clicking a link for example).

{% include gallery id="gallery1" type="center" %}

## Third-party cookies

**Third-party cookies** are cookies associated with a different domain than the one the user is currently looking at. If you ever wondered how target advertisment works, it's all about third-party cookies! :mag:

{% include gallery id="gallery2" type="center" %}

**Note:** Based on original learning material from [Mozilla](https://developer.mozilla.org/) engineers.
{: .notice--info}
