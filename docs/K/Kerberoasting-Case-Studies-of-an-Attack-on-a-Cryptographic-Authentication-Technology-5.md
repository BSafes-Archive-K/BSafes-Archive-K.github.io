---
layout: default
title: Mitigation of Kerberoasting 
parent: § Kerberoasting - Case Studies of an Attack on a Cryptographic Authentication Technology  
grand_parent: K
nav_order: 50 
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

## Mitigation of Kerberoasting
Fortunately, MITRE ATT&CK identifies ways to mitigate against a Kerberoasting attack. The first is encrypting sensitive information (Praetorian, 2022). Kerberoasting is, in part, successful because of the weak RC4 encryption. AES is now offered as a Kerberos encryption option, which is beneficial because of the stronger hashing it employs (Metcalf, 2015, 2017a). Therefore, AES Kerberos encryption, or another encryption standard similar in strength, should be used in place of RC4 encryption wherever possible (Praetorian, 2022).

The second is implementing strong password policies. Password requirements should dictate that passwords are changed regularly and at least 25 characters long, preferably 30 or more, which increases the difficulty of cracking (Metcalf, 2015, 2017a; Praetorian, 2022). Practicing password rotation puts time constraints on attackers attempting to decrypt long, complex passwords (*Qomplx Knowledge: Kerberoasting Attacks Explained,* 2021). Managed Service Accounts and Group Managed Service Accounts can help ensure that passwords meet the length and strength requirements and change regularly. An additional solution is employing a third-party technology to securely store passwords in a password management software (i.e., a vault) and using that vault to sign into other accounts (Metcalf, 2015, 2017a; Praetorian, 2022). It is crucial to evaluate any third-party password management tool considering that the associated service account would likely require Domain Administrator rights (Metcalf, 2017a).

The third mitigation recommendation from MITRE ATT&CK is privileged account management. It is not uncommon for service accounts to be over-privileged, having full administrator rights to Active Directory when not required (Metcalf, 2015, 2017a). Service accounts should follow the principle of least privilege and the minimal access necessary to perform their function. This includes privileged group membership such as Domain Administrators (Praetorian, 2022).

***

#### Table of Contents
{: .no_toc}

<ul><li> <a href="/docs/K/Kerberoasting-Case-Studies-of-an-Attack-on-a-Cryptographic-Authentication-Technology-1/">Introduction</a></li><li> <a href="/docs/K/Kerberoasting-Case-Studies-of-an-Attack-on-a-Cryptographic-Authentication-Technology-2/">Literature Review</a></li><li> <a href="/docs/K/Kerberoasting-Case-Studies-of-an-Attack-on-a-Cryptographic-Authentication-Technology-3/">Kerberoasting Case Studies</a></li><li> <a href="/docs/K/Kerberoasting-Case-Studies-of-an-Attack-on-a-Cryptographic-Authentication-Technology-4/">Detecting Kerberoasting Attacks</a></li><li> <a href="/docs/K/Kerberoasting-Case-Studies-of-an-Attack-on-a-Cryptographic-Authentication-Technology-5/">Mitigation of Kerberoasting</a></li><li> <a href="/docs/K/Kerberoasting-Case-Studies-of-an-Attack-on-a-Cryptographic-Authentication-Technology-6/">Policy Implications</a></li><li> <a href="/docs/K/Kerberoasting-Case-Studies-of-an-Attack-on-a-Cryptographic-Authentication-Technology-7/">Conclusion</a></li><li> <a href="/docs/K/Kerberoasting-Case-Studies-of-an-Attack-on-a-Cryptographic-Authentication-Technology-8/">References</a></li></ul>

***

</div>
