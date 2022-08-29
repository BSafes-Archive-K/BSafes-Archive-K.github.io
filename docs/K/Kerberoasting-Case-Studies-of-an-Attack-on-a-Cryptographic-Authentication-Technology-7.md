---
layout: default
title: Conclusion   
parent: § Kerberoasting - Case Studies of an Attack on a Cryptographic Authentication Technology 
grand_parent: K
nav_order: 70 
---
<style>
.dont-break-out {
  /* These are technically the same, but use both */
  overflow-wrap: break-word;
  word-wrap: break-word;

     -ms-word-break: break-all;
  /* This is the dangerous one in WebKit, as it breaks things wherever */
  word-break: break-all;
  /* Instead use this non-standard one: */
  word-break: break-word;
}

.youtube-container {
    position: relative;
    width: 100%;
    height: 0;
    padding-bottom: 56.25%;
}
.youtube-video {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
}

</style>

<div class="dont-break-out" markdown="1">

1. TOC
{:toc}

## Conclusion
Network security is crucial because, while the internet can be a treasure trove of information and resources, it ultimately falls short in terms of safety. One way of ensuring network security is through authentication. There are many methods and protocols for authentication exchange depending on the application and security requirements, such as Kerberos, which is designed to provide a way for a client and a server to authenticate each other’s identities using cryptography over an insecure network. While Kerberos has several benefits, it may be vulnerable to Kerberoasting attacks if a bad actor already has access to a compromised system. Although Kerberoasting cannot be performed against a host-based account due to the strong password policies, it is useful against domain user accounts because of weak passwords protected by equally weak encryption.

Based on the review of eCrime groups and the common TTPs, the most robust protection against Kerberoasting is a Defense in Depth approach. This approach should include both detection and mitigating factors. Tracking and reviewing filtered logs is the best way to detect Kerberoasting attempts. Another way to detect Kerberoasting attempts is to create a honeypot account. An attempt to access the honeypot is a good indication of a Kerberoasting attempt considering that there is no reason to access the account. Lastly, third-party applications can also provide monitoring services. Mitigation of Kerberoasting can be achieved in three ways: employing more robust Kerberos encryption (e.g., AES), implementing strong password policies, and managing service accounts based on the principle of least privilege.

In conclusion, while Kerberoasting poses a threat to the Kerberos authentication process, there are a few simple implementations that can mitigate these attacks, thereby rendering the authentication process much more secure. Implementation of these measures, coupled with other defensive measures geared toward other common attack vectors and a sharing of information between enterprises, can, at most, help an enterprise avoid a breach altogether; and, at least, give the defense team time to react to an attack as it is happening and mitigate the outcome.

***

#### Table of Contents
{: .no_toc}

<ul><li> <a href="/docs/K/Kerberoasting-Case-Studies-of-an-Attack-on-a-Cryptographic-Authentication-Technology-1/">Introduction</a></li><li> <a href="/docs/K/Kerberoasting-Case-Studies-of-an-Attack-on-a-Cryptographic-Authentication-Technology-2/">Literature Review</a></li><li> <a href="/docs/K/Kerberoasting-Case-Studies-of-an-Attack-on-a-Cryptographic-Authentication-Technology-3/">Kerberoasting Case Studies</a></li><li> <a href="/docs/K/Kerberoasting-Case-Studies-of-an-Attack-on-a-Cryptographic-Authentication-Technology-4/">Detecting Kerberoasting Attacks</a></li><li> <a href="/docs/K/Kerberoasting-Case-Studies-of-an-Attack-on-a-Cryptographic-Authentication-Technology-5/">Mitigation of Kerberoasting</a></li><li> <a href="/docs/K/Kerberoasting-Case-Studies-of-an-Attack-on-a-Cryptographic-Authentication-Technology-6/">Policy Implications</a></li><li> <a href="/docs/K/Kerberoasting-Case-Studies-of-an-Attack-on-a-Cryptographic-Authentication-Technology-7/">Conclusion</a></li><li> <a href="/docs/K/Kerberoasting-Case-Studies-of-an-Attack-on-a-Cryptographic-Authentication-Technology-8/">References</a></li></ul>

***

</div>
