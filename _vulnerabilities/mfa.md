---
layout: single
author_profile: false
title: "Hacking MFA"
excerpt: "MFA enabled? Almost there!"
sidebar:
  nav: "vulnerabilities"
header:
  teaser: /assets/images/hacking mfa/Mfa bypass-small.png
gallery1:
  - url: /assets/images/hacking mfa/Pwd attacks.png
    image_path: assets/images/hacking mfa/Pwd attacks.png
gallery2:
  - url: /assets/images/hacking mfa/Mfa bypass.png
    image_path: assets/images/hacking mfa/Mfa bypass.png
---

## Passwords are the worst! :triumph:

Passwords are the most common type of authentication, however they are also poorly efficient for security.
- New password policies are published almost every year, and always come up with changing requirements: complexity, length, rotation, reuse, passphrase… We are compelled to remember hundreds of passwords, and efficient cloud-based password managers are very often not allowed. :sob:
- Passwords are also costly as they bully IT support teams with endless password resets. :dollar:
- Furthermore, most of the attacks don’t even care about password complexity because they already have the full password available (black-market credential leakage exploiting reused passwords, phishing, keystroke logging, writing on a post note… :dizzy_face:). Clipping levels already protect against basic password spraying attacks on authentication forms. Complexity only protects against bruteforce attacks against stolen hash files. :page_facing_up:

In the end, **passwords are not secure**.

{% include gallery id="gallery1" type="center" %}

**Note:** Yet another punchline: **Hackers don’t break in, they log in!** Refer to [this excellent article](https://techcommunity.microsoft.com/t5/microsoft-entra-azure-ad-blog/your-pa-word-doesn-t-matter/ba-p/731984?country=us&culture=en-us).
{: .notice--warning}

## Hacking the MFA

Not all MFA are equal. And almost all of them are **breakable**. Let's collate some efficient techniques!
- Real-time phishing: Kindly ask for an OTP… or politely ask to accept a push notification :fishing_pole_and_fish:
- Real-time phishing: Send fake URL imitating the authentication page, and intercept the second factor
- Channel-jacking: Take over the channel used to provide the second factor (SMS or email)
- MFA fatigue (MFA bombing, MFA spamming)
- SIM swap :iphone:
- Compromised or stolen end-user device (spyware such as keylogger, rogue application)
- Abuse weak verification (false positives on fingerprints, use generative AI…)
- Capture victim physical attributes (record voice, collect fingerprint…) :paw_prints:
- Use the password recovery procedure
- Post authentication token stealing
- Physical attack (coercion, with force, weapon…) :gun:

Below is a modelling of real-time phishing with an Adversary-in-the-Middle (AitM) attack.

{% include gallery id="gallery2" type="center" %}

**Note:** Based on original learning material from [Government of Canada](https://www.cyber.gc.ca/en/guidance/defending-against-adversary-middle-threats-phishing-resistant-multi-factor-authentication-itsm30031).
{: .notice--info}
