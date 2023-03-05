---
layout: single
author_profile: false
title: "TLS 1.3"
excerpt: "Brush up on the basics!"
sidebar:
  nav: "protocols"
header:
  teaser: /assets/images/tls/TLS 1.3-small.png
gallery1:
  - url: /assets/images/tls/TLS 1.2.png
    image_path: assets/images/tls/TLS 1.2.png
gallery2:
  - url: /assets/images/tls/TLS 1.3.png
    image_path: assets/images/tls/TLS 1.3.png
---
## Introduction

The **Transport Layer Security** (TLS) protocol ensures the security of network flows over an untrusted network. It operates at presentation layer, and secures several application layer protocols: **HTTPS**, but also FTPS, SMTPS, IMAPS, POP3S, DoT… It provides the following security properties:
- **Confidentiality** of application data
- **Integrity** of application data
- **Anti-replay** of application data
- **Authentication** of the server
- **Authentication** of the client (optional)

**Note:** TLS does not offer non-repudiation of exchanged data.
{: .notice--warning}

Let's start with a brief overview of the TLS handshake process. For the sake of clarity, the **TLS 1.2 handshake** is represented below since the different steps are easier to understand.

{% include gallery id="gallery1" type="center" %}

## Cryptographic fun

### TLS 1.3 handshake

Let's continue with a more detailed modelling, in order to identify the handshake crypto magic. The client initiates the TLS handshake by listing the supported cryptographic algorithms. The server answers with the selected protocols.

**Note:** The TLS 1.2 handshake consists in at least 5 packets sent back-and-forth. But **TLS 1.3 speeds up the handshake** by limiting it to 3. :rocket:
{: .notice--warning}

{% include gallery id="gallery2" type="center" %}

### TLS 1.3 explanations

| Parameter                                       | Explanation                  |
| ----------------------------------------------- | ---------------------------- |
| Random:<br/>*68a9ddc224...*                     | Random value used to prevent protocol version degradation attacks. |
| Server Name:<br/>*kartapuce.com*                | With this Server Name Indication, the server specifies the desired domain name. It is useful when several domain names are hosted behind a single IP address. <br /> :memo: **Note:** When the SNI is provided in the Client Hello message, it is not encrypted, which may raise privacy concerns since anybody intercepting the traffic can obtain this information. Therefore, **some TLS 1.3 extensions permit to encrypt the SNI**. When used in combination with DNS over TLS, it provides much better privacy. :mag: |
| Supported Version:<br/>*TLS 1.3*                | This is the latest TLS version, without known vulnerabilities. |
| Cipher Suite:<br/>*TLS_AES_256_GCM_SHA384*      | The AES_256_GCM cipher suite provides confidentiality and integrity of the application data. The SHA384 hash algorithm is used with HKDF in order to derivate the secret keys. <br /> :memo: **Note:** **TLS 1.3 removes unsecure cipher suites** such as AES_256_CBC which rely on CBC mode ciphers. Unsecure hash algorithms such as SHA-1 or MD5 are also removed. |
| PSK Key Exchange Modes:<br/>*PSK_DHE_KE*        | The key establishment relies on the Eliptic Curve Ephemeral Diffie-Hellman key establishment protocol. The Diffie-Hellman key exchange is ephemeral because a new session key is computed for each key exchange (based on random client and server parameters). The Diffie-Hellman also provides Perfect Forward Secrecy: if Kartapuce Private key is compromised in the future (long-term secret), it is still not possible to retrieve old session keys from captured traffic. <br /> :memo: **Note:** Using ephemeral key exchange implies that passive TLS inspection is no more feasible. :monkey: TLS inspection must now be performed inline. |
| Key Share Group:<br/>*x25519*                   | It uses the x25519 elliptic curve. |
| Signature Algorithms:<br/>*RSA_PSS_RSAE_SHA256* | The server is authenticated during the key exchange, preventing man-in-the-middle attacks. <br /> :memo: **Note:** The selected signature algorithm is not indicated in the clear-text Server Hello. A simple inspection of the X.509 certificate provided by the server permits to determine the algorithm. |
| Certificate                                     | This contains the X.509 certificate of the server. <br /> :memo: **Note:** In order to increase privacy, **TLS 1.3 encrypts the server certificate**, so that passive eavesdropping does not permit to discover the visited website. In order to respect the regulation, TLS interception performs policy-based interception decisions based on the server certificate. This is not possible anymore with TLS 1.3. |

**Note:** Wireshark permits to capture and analyse the TLS handshake. :fish:
{: .notice--warning}

**Note:** Based on original learning material from [ANSSI](https://www.ssi.gouv.fr) documentation *Recommandations de sécurité relatives à TLS*.
{: .notice--info}
