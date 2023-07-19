---
layout: single
author_profile: false
title: "Authentication schemes"
excerpt: "A review of authentication schemes."
sidebar:
  nav: "protocols"
header:
  teaser: /assets/images/auth/pass.png
gallery1:
  - url: /assets/images/auth/pass.png
    image_path: assets/images/auth/pass.png
gallery2:
  - url: /assets/images/auth/mTLS.png
    image_path: assets/images/auth/mTLS.png
---
## Introduction

All the authentication schemes rely on one of 3 authentication means:
- **password**: the user proves its identity by disclosing its password (a shared secret). Depending on the authentication scheme, the user authenticates by disclosing a password or passphrase (basic authentication), the hash of a password (digest authentication or NTLM), an API key, or a token for a web app… It can be permanent or temporary (nonce).
- **symmetric cryptography**: the user proves its identity by performing a cryptographic operation based on a shared secret (a symmetric key). Based on the authentication scheme, the user generates a keyed-hash message authentication code (HMAC), or the output of a symmetric-key algorithm (AES). The message can be complemented with additional information (JWS bearer with HMAC is just a string with more information). The symmetric key may even directly derivate from a password with a Key Derivation Function (KDF).
- **asymmetric cryptography**: the user proves its identity by performing a cryptographic operation based on a private secret and a disclosed value (a public / private key). Based on the authentication scheme, it can be the output of an asymmetric-key algorithm (RSA or ECDSA), and can be complemented by a digital certificate (TLS).

**Note:** A lot of authentication schemes (protocols) exist for authentication. Some of them rely on direct transmission of the secret, while others use a challenge – response pattern. An authentication scheme may allow for several authentication means. For example, Kerberos may work with both symmetric or asymmetric cryptography. Depending on the protocol, the authentication may be performed at a different OSI layer (application layer for basic authentication, transport layer for TLS, datalink layer for Radius 802.1X).
{: .notice--warning}

## Type 1: « What I know » :zipper_mouth_face:

Something that I can remember. The easiest example is the password. An API Key may also be used, but it is stored in a safe when its size is too long to remember. While it is by far the most common type of authentication, it is also considered as the weakest (weak passwords, reused on several applications...).

## Type 2: « What I have » :iphone:

A lot of different technologies already exist:
- **TOTP (Time-Based OTP)**: nonce incremented every 30 seconds (Google Authenticator)
- **HOTP (Hash-based OTP)**: nonce incremented on each pressure (Yubikey)
- **POTP (Push OTP)**: nonce not even disclosed to the user generated on approval (Boursorama)
- **SMS**: nonce received on a smartphone. Vulnerable to SIM fraud (it is trivial to copy a SIM card!) and not considered safe.
- **Chip card**: private key securely stored in a physical device, non exportable.

Authentication devices may use different protocols for exchanging information (bluetooth, NFC, USB…).

## Type 3: « Who I am » :eyes:

A biometric parameter: a shared measurement (the position of points on a fingerprint or a face, the modulation of a voice…). It is considered more secure than a password, but it is not revokable, and may be publicly available to anyone.

## Multi-Factor Authentification :zipper_mouth_face: :heavy_plus_sign: :eyes: :heavy_plus_sign: :iphone:

In case of **multi-factor authentication** relying  on proof of knowledge and proof of owning, the 2FA is often combined as:
- the password is directly input in the physical device, in order to unlock the embedded secret. The physical device is therefore accountable for the verification of the proof of knowledge.
- the password and the physical device both send independently their secret to the authentication server.

**Note:** MFA does not necessarily provide **strong authentication**. For example, a 2FA based on a password and an SMS is not secure.
{: .notice--warning}

# There is something about passwords.

## Passwords are the worst! :triumph:

Passwords are the most common type of authentication, however they are also poorly efficient for security.
- New password policies are published almost every year, and always come up with changing requirements: complexity, length, rotation, reuse, passphrase… We are compelled to remember hundreds of passwords, and efficient cloud-based password managers are very often not allowed. :sob:
- Passwords are also costly as they bully IT support teams with endless password resets. :dollar:
- Furthermore, most of the attacks don’t even care about password complexity because they already have the full password available (black-market credential leakage exploiting reused passwords, phishing, keystroke logging, writing on a post note… :dizzy_face:). Clipping levels already protect against basic password spraying attacks on authentication forms. Complexity only protects against bruteforce attacks against stolen hash files. :page_facing_up:

In the end, **passwords are not secure**.

**Note:** Yet another punchline: **Hackers don’t break in, they log in!** Refer to [this excellent article](https://techcommunity.microsoft.com/t5/microsoft-entra-azure-ad-blog/your-pa-word-doesn-t-matter/ba-p/731984?country=us&culture=en-us).
{: .notice--warning}

## Let’s go ~~wild~~ passwordless :dancer:

The purpose of **passwordless** is to eradicate the use of passwords. The process still uses MFA, but mostly relies on authentication and biometric factors. The **FIDO2** specifications illustrate how the combination of a possession factor (such as software *Authenticator* app, or hardware *Yubikey*) and a biometric factor (fingerprint, face picture) drastically improve security. Once enrolled, the token securely stores a private key, which is only disclosed when this second factor is locally verified.

**Note:** Let’s fight a common misconception! :punch: PINs, in the context of passwordless, are much more secure than passwords, because they never leave the endpoint device. Therefore, it reduces the risk associated with stolen credential files, or phishing emails.
{: .notice--warning}

## Examples of authentication schemes

### Password-based authentication

Let's assume that Alice wants to authenticate with her very strong passphrase "*password*"! :stuck_out_tongue_closed_eyes:

{% include gallery id="gallery1" type="center" %}

### Cryptographic authentication

{% include gallery id="gallery2" type="center" %}

A session key is obtained with a combination of ECDHE 256 bits and ECDSA 256 bits. Then, this session key protects the session with AES 256 bits. :lock:

**Note:** It is not recommended to directly transmit a session key with RSA because it does not provide **Perfect Forward Secrecy**. If strictly required, RSA 2048 bits shall be used. **Ephemeral Diffie-Hellman** permits to obtain a shared secret over a public channel, with perfect forward secrecy property. But it is vulnerable to man in the middle, so it is used in combination with ECDSA for authentication.
{: .notice--warning}

**Note:** Based on original learning material from [ANSSI](https://www.ssi.gouv.fr/) documentation *Recommendations relatives à l'authentification multifacteur et aux mots de passe*, and from [Microsoft](https://www.microsoft.com) report *Passwordless protection: Reduce your risk exposure with passwordless authentication*.
{: .notice--info}
