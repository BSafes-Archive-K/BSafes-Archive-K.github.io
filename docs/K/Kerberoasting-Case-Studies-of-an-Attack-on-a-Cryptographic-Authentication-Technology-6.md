---
layout: default
title:  Policy Implications  
parent: § Kerberoasting - Case Studies of an Attack on a Cryptographic Authentication Technology  
grand_parent: K
nav_order: 60 
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

## Policy Implications
Based on the cases discussed in this paper, it is clear that Kerberoasting is used as a steppingstone to help achieve a more significant and more detrimental attack. Oftentimes, the goal of the overall attack is to encrypt a system and hold it for ransom, as seen with Carbon Spider, Nobelium, and Wizard Spider. When facing ransomware, there are generally only two outcomes: (a) the enterprise pays a significant ransom to regain access to their files, or (b) the enterprise does not pay and loses access to their data forever. However, as seen in the Fox-IT case, ransomware is not the only attack in which Kerberoasting can play a role. Kerberoasting can also be used to help an attacker quietly copy data from a domain before evacuating. In turn, this data can be used against an enterprise or sold on data leak sites. Either option will likely cause the enterprise money and resources. Considering that Kerberoasting is part of an attack arsenal and not a substantial threat on its own, the question becomes: is it worth defending against Kerberoasting attacks? The short answer is YES.

A common term used in the world of cybersecurity is Defense in Depth. The Defense in Depth approach is frequently referenced by the National Institute of Standards and Technology (NIST) in several of their publications (Computer Security Resource Center, n.d.). The Center for Internet Security (CIS) explains that a goal of a Defense in Depth approach is redundancy within network security with the aim of preventing any single point of failure. One of the ways it achieves this is by increasing the time and complexity needed to compromise a network successfully. In turn, this not only depletes the resources of the bad actors but also makes it more likely that an active attack can be identified and addressed before its completion (Center for Internet Security, n.d.).

This is not a new approach to securing valuable assets (Center for Internet Security, n.d.). Defense in Depth approach can be seen in countless security measures today, such as homes surrounded by fences, and equipped with locked doors; video-monitoring doorbells; a security system; or banks with a security guard, protective glass in front of the tellers, time-controlled safes, and panic buttons. We can even look back in history and see this method used with the outer walls, moats, towers, lookout points, and drawbridges in castles (Cyber Edu, n.d.).

Practically, the architecture of a Defense in Depth approach can be broken down into physical controls, technical controls, and administrative controls. Physical controls prevent physical access to information and communications technology (ICT) systems. Technical controls protect network systems, hardware, and software.

Administrative controls are comprised of policies and procedures for employees. Additional security layers that may help protect different elements of a network include access measures, workstation defenses, data protection, perimeter defenses, and monitoring and prevention (*Defense-in-Depth*, n.d.).

With a Defense in Depth approach in mind, it becomes easier to see how preparing defenses against Kerberoasting and other small tools used in more significant attacks can help on a bigger scale. By strengthening the Kerberos network authentication protocol, an enterprise can halt an attack by removing the adversary’s ability to harvest credentials and achieve lateral or upward movement, or persistence. Suppose a stronger Kerberos protocol does not circumvent an attack. In that case, it may give the defense team time to prepare and react to an attack by delaying the speed with which an adversary is able to navigate through their domain. As seen with the Carbon Spider and Wizard Spider ransomware attacks, time is valuable. If an adversary is able to compromise an enterprise’s system from start to finish within a matter of a few hours, that limits the defense team’s ability to protect their assets. Detection of a Kerberoasting attempt is comparable to an early warning system. As indicated in the case studies, Kerberoasting is typically deployed earlier in the attack considering it is usually used to maintain persistence, move laterally, or escalate privilege, which is often needed to continue into the next stages of an attack (Medin, 2014; Praetorian, 2022). Coupled with the fact that Kerberoasting is a good indicator that an adversary has a larger goal, and therefore attack, in mind, both detection and mitigation of Kerberoasting provide an enterprise’s cybersecurity team with a couple of solid layers of defense.

ICT has experienced rapid growth and development over the last few decades. As technology advances, so do attack vectors created and used by bad actors. Currently, a limited number of post-attack reports are publicly shared by enterprises after they have suffered an incident. NIST’s Computer Security Incident Handling Guide summarizes the incident response cycle in four steps: (1) preparation; (2) detection and analysis; (3) containment, eradication, and recovery and; (4) post-incident activity. They say that one of the essential parts of incident response is that final step, specifically learning and improving. It can help an enterprise enhance security measures and adapt to evolving technologies and threats. NIST notes that information sharing between enterprises is the most important element of incident response coordination (Cichonski et al., 2012).

Enterprises often face the same threats, especially within the same industry. Sharing information can be beneficial across the board. If a cybersecurity expert sees suspicious activity in their environment, they should be able to share that with their industry and see what other cybersecurity experts from other enterprises may be doing in response. If more enterprises were willing to share their reports, it would help to shed light on the TTPs used across adversary groups. Analyzing each of these attacks next to one another may assist enterprises in increasing their detection and mitigation defenses, thereby limiting the impact caused by these attacks.

***

#### Table of Contents
{: .no_toc}

<ul><li> <a href="/docs/K/Kerberoasting-Case-Studies-of-an-Attack-on-a-Cryptographic-Authentication-Technology-1/">Introduction</a></li><li> <a href="/docs/K/Kerberoasting-Case-Studies-of-an-Attack-on-a-Cryptographic-Authentication-Technology-2/">Literature Review</a></li><li> <a href="/docs/K/Kerberoasting-Case-Studies-of-an-Attack-on-a-Cryptographic-Authentication-Technology-3/">Kerberoasting Case Studies</a></li><li> <a href="/docs/K/Kerberoasting-Case-Studies-of-an-Attack-on-a-Cryptographic-Authentication-Technology-4/">Detecting Kerberoasting Attacks</a></li><li> <a href="/docs/K/Kerberoasting-Case-Studies-of-an-Attack-on-a-Cryptographic-Authentication-Technology-5/">Mitigation of Kerberoasting</a></li><li> <a href="/docs/K/Kerberoasting-Case-Studies-of-an-Attack-on-a-Cryptographic-Authentication-Technology-6/">Policy Implications</a></li><li> <a href="/docs/K/Kerberoasting-Case-Studies-of-an-Attack-on-a-Cryptographic-Authentication-Technology-7/">Conclusion</a></li><li> <a href="/docs/K/Kerberoasting-Case-Studies-of-an-Attack-on-a-Cryptographic-Authentication-Technology-8/">References</a></li></ul>

***

</div>
