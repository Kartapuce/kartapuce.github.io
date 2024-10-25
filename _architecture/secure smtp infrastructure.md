---
layout: single
author_profile: false
title: "Secure SMTP infrastructure"
excerpt: "Everything you've always wanted to know about SMTP."
sidebar:
  nav: "architecture"
header:
  teaser: /assets/images/Secure SMTP infrastructure-small.png
gallery1:
  - url: /assets/images/Secure SMTP infrastructure.png
    image_path: assets/images/Secure SMTP infrastructure.png
---

## Architecture

This modelling aims at describing the different components that are part of a **Simple Mail Transfer Protocol (SMTP)** infrastructure, and their location within a secure gateway.

:x: It highlights several well-known attacks on an SMTP infrastructure:
- disclosure of confidential data,
- spoofing of identity,
- typosquatting / malware / phishing / DoS,
- disclosure or alteration of email content.

:heavy_check_mark: And it identifies the means to protect:
- SMTPS / IMAPS / STARTTLS,
- DKIM / SPF,
- attached-file analysis / SPAM detection / email quarantines / whitelisting,
- end-to-end integrity and confidentiality.

## Use Case

In this example, let's consider the user Bob. He is a valuable member of Kartapuce, and belongs to the kartapuce.com domain. Bob wants to send IOCs to his colleague Jack, and to his friend Tom on his personal email.

Let's have a look at all the operations that happen under the wood! :stuck_out_tongue:

{% include gallery id="gallery1" type="center" %}

## Encryption, and receiving server authentication

By default, SMTP is not secure and sends the messages in plain text, without any authentication of the receiving server. :cry:

**SMTPS (Simple Mail Transfer Protocol Secure):** SMTPS is a method used to wrap SMTP inside TLS. SMTPS often starts with the STARTTLS command. However, this command only provides Opportunistic TLS (not Forced TLS). It is an efficient measure against passive eavesdropping. However, it is vulnerable to an active man-in-the-middle attack, since an attacker can easily pretend that TLS is not available in order to downgrade to plaintext SMTP protocol. :neutral_face: Additionally, even if the destination mail server supports TLS for encryption, a lot of servers provide expired TLS certificates, or certificates not issued by trusted third-parties. Therefore, the destination mail server is often not authenticated.

**MTA-STS (Mail Transfer Agent - Strict Transport Security):** MTA-STS aims at providing a security against TLS downgrade and man-in-the-middle attacks. The server specifies if it can handle MTA-STS in a DNS TXT record. Then, it publishes its STA-MTS policy in a dedicated endpoint (*"https://mta-sts.\<company\>.com/.well-known/mta-sts.txt"*) along with its MX record.
- As a **sending server**, the server will comply with the MTA-STS policy of the receiving server. If the receiving server does not support MTA-STS, the email will be sent anyway. Since we don’t control the MTA-STS policy of each receiving server, we cannot strictly ensure the authenticity of all the receiving servers at large.
- As a **receiving server**, with *“enforce”* mode, it is possible to force the use of TLS for emails sent to our domain by a sending server that supports MTA-STS. The receiving server will publicize its MTA-STS policy. If the sending server also complies with MTA-STS, it will only send the email if TLS is activated and the certificate is valid. :green_heart: If the sending server does not comply with MTA-STS, it will send the email anyway. Therefore, we offer a chance to a sending server to validate our authenticity (but don’t force him to do so). We did our job by offering a chance to authenticate us, now it’s their turn to make the proper checks. :cop:

**DANE (DNS-based Authentication of Named Entities):** DANE aims at providing a security against TLS downgrade and man-in-the-middle attacks. DANE relies on DNSSEC to retrieve a hash of the certificate of the receiving domain. The sending server can validate the authenticity of the receiving server certificate, by comparing it with the data provided in the TLSA DNS record. Therefore, there is no more dependency on CA for certificate validation.

## Phishing, and sending server authentication

The sender and the sending server of an email are not authenticated. :see_no_evil: An email is sent using an **SMTP envelope** (used for routing, such as the *“HELO”*, *“MAIL FROM”*, *“RCPT TO”* commands), and an **email header** (as displayed to the user: *“subject”*, *“from”*, *“to”*, *“cc”*…). Both the envelope and the headers can be forged. :no_good: Attackers take advantage of these vulnerabilities to abuse the users with:
- **Lookalike domains:** a domain close to the original one, but different. Example: *“k4artapuce.com”* instead of *“kartapuce.com”*
- **Display name spoofing:** an attacker forges the email headers. Example: *MAIL FROM attacker[at]gmail.com ; From: “CEO Kartapuce” <attacker[at]gmail.com>*
- **Domain spoofing:** an attacker tries to spoof the domain. Example: *MAIL FROM ceo[at]kartapuce.com ; From: “CEO Kartapuce” <ceo[at]kartapuce.com>*
- **Compromised account:** an attacker targets a user with poor cybersecurity measures to spoof its identity. Example: *FROM “Victim user” <victim[at]supplier.com>*

Consequently, several protocols were created to provide some form of authentication.

**SPF (Sender Policy Framework):** SPF is a protection against email spoofing. An SPF record is a DNS record, which contains a listing of IP addresses that are authorized to send emails for this domain. If the IP address used by the sending server does not belong to this list, the receiving server can drop the mail, or tag it as spam. However, SPF only checks the *"MAIL FROM"* attribute (aka *"return-path"*) of the SMTP envelope. :information_desk_person:

**DKIM (DomainKeys Identified Mail):** DKIM is a protection against email spoofing, based on public key cryptographic authentication. The sending server uses its private key to sign the message, and inserts this signature within the DKIM header. The receiving server retrieves the public key from the DKIM DNS record, and validates the signature. The signature is computed on header fields (*“from”*, *“to”*, *“subject”*) and a hash of the email body.

**DMARC (Domain-based Message Authentication Reporting and Conformance):** DMARC is a protection against email spoofing, built on top of SPF and DKIM. DMARC determines what to do after SPF and DKIM are checked. The DMARC policy is stored in a DNS TXT record. In case the message fails the SPF and DKIM controls, the DMARC policy can specify to do nothing, or to reject the email, or to quarantine it as spam. :no_entry:

**ARC (Authenticated Received Chain):** ARC is used to propagate SPF, DKIM and DMARC results when an intermediate server is involved in email delivery. Without ARC, a forwarder might break sender authentication, or DKIM signature when the message is modified for legitimate purposes.

**BIMI (Brand Indicators for Message Identification):** BIMI helps to validate the authenticity of a sending server. If a sending server provides a DMARC policy (*“quarantine”* or *“reject”*), and the DMARC checks are successful, the receiver will be able to display a logo of the sending domain. The BIMI is provided as a TXT DNS record, which indicates the URL to retrieve the logo. :art:

## End-to-end encryption

All the protocols listed above mostly relate to encryption and authentication from a sending server to a receiving server. However, the message is in plain text during each hop between servers. With end-to-end encryption, it is possible to ensure confidentiality and authenticity of the message, directly from the sender up to the receiver. :boom: The email can’t be read by anyone but the intended recipient. These technologies are based on public key cryptography. **PGP (Pretty Good Privacy)** and **S/MIME (Secure/Multipurpose Internet Mail Extensions)** provide such features. Some vendors also offer proprietary tools, that integrate more easily within their email solution.

**Note:** Based on original learning material from [ANSSI](https://www.ssi.gouv.fr/) documentation *Recommandations relatives à l’interconnexion d’un système d’information à Internet*, and from [Cloudflare](https://www.cloudflare.com/) engineers.
{: .notice--info}
