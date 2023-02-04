---
layout: single
author_profile: false
title: "Web App security risks"
excerpt: "Web applications security risks from the OWASP."
sidebar:
  nav: "vulnerabilities"
header:
  teaser: /assets/images/web/traversal.png
gallery1:
  - url: /assets/images/web/traversal.png
    image_path: assets/images/web/traversal.png
gallery2:
  - url: /assets/images/web/csrf.png
    image_path: assets/images/web/csrf.png
gallery3:
  - url: /assets/images/web/injection.png
    image_path: assets/images/web/injection.png
gallery4:
  - url: /assets/images/web/xss.png
    image_path: assets/images/web/xss.png
gallery5:
  - url: /assets/images/web/authentication.png
    image_path: assets/images/web/authentication.png
gallery6:
  - url: /assets/images/web/ssrf.png
    image_path: assets/images/web/ssrf.png
---

The **Open Web Application Security Project (OWASP)** Top 10 is a must-known for current most critical security risks on web applications. Let's review some of them, which may be hard to properly explain without some drawing! :paintbrush:

## Web Application Security Risks

*Category:* Broken Access Control  
*Type:* **Path traversal**, **Directory traversal**  
An attacker accesses files or directories that are stored outside of the web root folder.

{% include gallery id="gallery1" type="center" %}

*Category:* Broken Access Control  
*Type:* **Cross-Site Request Forgery (CSRF – Sea Surf)**  
An attacker tricks the victim into submitting a malicious request on a web application in which the victim is currently authenticated, in order to inherit its identity and privileges (user or administrator).

{% include gallery id="gallery2" type="center" %}

*Category:* Injection  
*Type:* **SQL / LDAP / CRLF injection**  
The attack takes advantage of poor user-supplied data sanitizing and validation to perform undesired actions on the applications (query, input, deletion of data in databases, log files…).

{% include gallery id="gallery3" type="center" %}

*Category:* Injection  
*Type:* **Cross Site Scripting (XSS)**  
Malicious scripts are injected into a trusted website, which get executed in the end user’s browser.  
**Stored XSS:** Persistent XSS since the malicious script is stored on the target server.  
**Reflected XSS:** Non-persistent XSS since the malicious script is immediatly returned by the target server.

{% include gallery id="gallery4" type="center" %}

*Category:* Identification and authentication failures  
*Type:* **Improper authentication**  
Due to authentication mechanisms, the attacker is able to access sensitive content without authentication.

{% include gallery id="gallery5" type="center" %}

*Category:* **Server-Side Request Forgery (SSRF)**  
Due to poor sanitazing and validation of client-supplied data, the attacker coerces the application to send an unexpected request to an unexpected destination.

{% include gallery id="gallery6" type="center" %}

**Note:** Based on original learning material from [OWASP Top 10](https://owasp.org/www-project-top-ten/) ranking. The original ranking is much more detailed: go for it!
{: .notice--info}
