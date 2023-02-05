---
layout: single
author_profile: false
title: "Zero Trust"
excerpt: "A long journey towards Zero Trust."
sidebar:
  nav: "architecture"
header:
  teaser: /assets/images/zero trust.png
gallery1:
  - url: /assets/images/zero trust.png
    image_path: assets/images/zero trust.png
---

Let's put some segmentation in our network, and review all the steps towards **Zero Trust**:
- Flat network: *That's just Open-bar man!* :beer:
- Perimeter-based segmentation: *802.1X and we're good to go.*
- Macro-segmentation: *Choose your VLAN wisely.* :detective: 
- Clustered segregation: *So much stuff behind that wall.*
- Micro-segmentation: *Let's get selective.*
- Zero Trust: *I just don't care where you are.* :dart:

**Note:** Each step provides cumulative additional protections to enforce.
{: .notice--warning}

The blue zone represents the trusted area. The black line demarcates the internal network.

{% include gallery id="gallery1" type="center" %}

**Note:** A review of the migration towards Zero Trust has been performed by the [ANSSI](https://www.ssi.gouv.fr/agence/publication/le-modele-zero-trust/).
{: .notice--info}
