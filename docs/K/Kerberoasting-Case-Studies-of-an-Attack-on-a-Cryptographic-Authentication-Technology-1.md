---
layout: default
title: Introduction
parent: § Kerberoasting - Case Studies of an Attack on a Cryptographic Authentication Technology 
grand_parent: K
nav_order: 10 
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

## Introduction
The internet is a vital aspect of everyday life for many worldwide, including individual users, small businesses, the government, and large enterprises. Compared to its popularity, the network security of the internet is relatively insecure. Attackers can identify unencrypted passwords from vulnerable applications using password sniffing tools. In addition, many client/server applications mainly require the client to restrict its activities while the server rarely imposes any restrictions. Firewalls or authentication technologies have been implemented to accommodate better network security and minimize the existing limitations.

Among various network security approaches, this paper focuses on authentication technology, specifically a cryptographic authentication called Kerberos and its related targeted attack called Kerberoasting. Cryptographic authentication allows clients and servers to securely prove their identities before conducting business with one another to help prevent a breach. Kerberos is a specific network authentication protocol that uses cryptography to allow a client and server to verify each other over the network before providing the client access to the requested resource. Kerberoasting is the attack vector aimed at the Kerberos authentication protocol.

Kerberos authentication protocol was developed with security in mind. Even so, it is still vulnerable to attacks (Praetorian, 2022). MITRE ATT&CK is a knowledge base of Tactics, Techniques, and Procedures(TTP)

***
*Corresponding author
{: .fs-2}
D Demers*, Acting Director of Equal Opportunity, Office of Equal Opportunity Bridgewater State University, Boyden Hall 206, 131
Summer St., Bridgewater, MA, 02325, U.S.A.
Email: d1demers@bridgew.edu
{: .fs-2}
Reproduction, posting, transmission or other distribution or use of the article or any material therein, in any medium as permitted by written agreement of the International Journal of Cybersecurity Intelligence and Cybercrime, requires credit to the Journal as follows: “This Article originally appeared in International Journal of Cybersecurity Intelligence and Cybercrime (IJCIC), 2022 Vol. 5, Iss. 2, pp. 25-39” and notify the Journal of such publication.
{: .fs-2}
© 2022 IJCIC 2578-3289/2022/08
{: .fs-2}
***

used by bad actors, which are used to create threat models for the cybersecurity community (MITRE ATT&CK, n.d.). MITRE ATT&CK currently lists four sub-techniques that may be used to forge or steal Kerberos tickets: Golden Ticket, Silver Ticket, Kerberoasting, and AS-REP Roasting (Praetorian, 2022). Therefore, while addressing the importance of Kerberos, this paper also focuses on Kerberoasting because there is a low investment for the attacker (i.e., it is a simple attack). If successful, Kerberoasting offers a great reward, such as lateral movement, escalated privileges, or persistence in a system. Considering the devastating damage that can be caused by a successful Kerberoasting attack, it is vital to understand not only how the attack works but how to defend against and mitigate attack attempts. While information about Kerberos and Kerberoasting is available across multiple resources, there is a lack of case studies in the literature to help gain an overall understanding of the real-life application and threat posed by this attack. The subsequent sections of this paper will cover a literature review of network security and cryptography, how Kerberos works, Kerberoasting methods, a case studies, detection and mitigation, and policy implications.

***

#### Table of Contents
{: .no_toc}

<ul><li> <a href="/docs/K/Kerberoasting-Case-Studies-of-an-Attack-on-a-Cryptographic-Authentication-Technology-1/">Introduction</a></li><li> <a href="/docs/K/Kerberoasting-Case-Studies-of-an-Attack-on-a-Cryptographic-Authentication-Technology-2/">Literature Review</a></li><li> <a href="/docs/K/Kerberoasting-Case-Studies-of-an-Attack-on-a-Cryptographic-Authentication-Technology-3/">Kerberoasting Case Studies</a></li><li> <a href="/docs/K/Kerberoasting-Case-Studies-of-an-Attack-on-a-Cryptographic-Authentication-Technology-4/">Detecting Kerberoasting Attacks</a></li><li> <a href="/docs/K/Kerberoasting-Case-Studies-of-an-Attack-on-a-Cryptographic-Authentication-Technology-5/">Mitigation of Kerberoasting</a></li><li> <a href="/docs/K/Kerberoasting-Case-Studies-of-an-Attack-on-a-Cryptographic-Authentication-Technology-6/">Policy Implications</a></li><li> <a href="/docs/K/Kerberoasting-Case-Studies-of-an-Attack-on-a-Cryptographic-Authentication-Technology-7/">Conclusion</a></li><li> <a href="/docs/K/Kerberoasting-Case-Studies-of-an-Attack-on-a-Cryptographic-Authentication-Technology-8/">References</a></li></ul>

***

</div>
