---
layout: default
title: Detecting Kerberoasting Attacks
parent: § Kerberoasting - Case Studies of an Attack on a Cryptographic Authentication Technology  
grand_parent: K
nav_order: 40 
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

## Detecting Kerberoasting Attacks
According to MITRE ATT&CK, logging Kerberos TGS service ticket requests using Audit Kerberos Service Ticket Operations is one way to detect a Kerberoasting attack. When deploying this method, particular attention should be paid to any suspicious activity patterns, such as accounts making several requests in a short period of time, especially if the account also requested RC4 encryption (Praetorian, 2022). The logs of these events should be filtered for Kerberos TGS service tickets with RC4 hash encryption (Type 0x17) and sent into a Security Information and Event Management (SIEM) tool. Additional filters can include excluding requests from service accounts, turning on Audit Success, and excluding requests for service names, including a $ (Metcalf, 2017b).

Another option is to deploy a honeypot account with a fake but unique SPN. A honeypot is a fake account intentionally designed to be alluring to an adversary that can be used to detect suspicious activity. Any request for the honeypot account’s fake SPN will not be valid, indicating that it is malicious. It is beneficial to make this honeypot account more enticing. Two ways to do that are to set the AdminCount attribute to one, signifying that the account may have elevated rights, and by adding the account to fake groups to create the impression that it is granting additional elevated rights. Once the account is live, any attempt to access it should be investigated. As the account is fake and is not linked to any real application, there is no reason to request a TGS service ticket. Therefore, it is probable that anyone trying to request such a ticket is deploying a Kerberoast attack on the fake account (Metcalf, 2017b).

A third option is to employ the use of a third-party monitoring technology such as those offered by Qomplx or Awake Security Platform. Qomplx technology watches for Kerberoasting attack signs, such as Event ID 4769. They offer a Privilege Assurance tool, which operates on the principle of least privilege, minimizing the chance of service accounts having too many permissions. Qomplx also monitors Windows Event Logs for suspicious activity and compares them to other logs in order to establish behavioral indicators of attempted Kerberoasting activity (*Qomplx Knowledge: Kerberoasting Attacks Explained*, 2021). Awake Security Platform utilizes an abstraction layer that allows them to analyze Lightweight Directory Access Protocol (LDAP) search Request messages and Kerberos authentication protocol data to identify suspicious activity. When the Awake Security Platform identifies a suspicious activity, it uses a graphical representation to show that there was a Kerberoasting attempt (Ghosal, n.d.). Enterprises seeking the services of a third-party platform should research options, request demos, and make a determination based on their enterprise needs.

***

#### Table of Contents
{: .no_toc}

<ul><li> <a href="/docs/K/Kerberoasting-Case-Studies-of-an-Attack-on-a-Cryptographic-Authentication-Technology-1/">Introduction</a></li><li> <a href="/docs/K/Kerberoasting-Case-Studies-of-an-Attack-on-a-Cryptographic-Authentication-Technology-2/">Literature Review</a></li><li> <a href="/docs/K/Kerberoasting-Case-Studies-of-an-Attack-on-a-Cryptographic-Authentication-Technology-3/">Kerberoasting Case Studies</a></li><li> <a href="/docs/K/Kerberoasting-Case-Studies-of-an-Attack-on-a-Cryptographic-Authentication-Technology-4/">Detecting Kerberoasting Attacks</a></li><li> <a href="/docs/K/Kerberoasting-Case-Studies-of-an-Attack-on-a-Cryptographic-Authentication-Technology-5/">Mitigation of Kerberoasting</a></li><li> <a href="/docs/K/Kerberoasting-Case-Studies-of-an-Attack-on-a-Cryptographic-Authentication-Technology-6/">Policy Implications</a></li><li> <a href="/docs/K/Kerberoasting-Case-Studies-of-an-Attack-on-a-Cryptographic-Authentication-Technology-7/">Conclusion</a></li><li> <a href="/docs/K/Kerberoasting-Case-Studies-of-an-Attack-on-a-Cryptographic-Authentication-Technology-8/">References</a></li></ul>

***

</div>
