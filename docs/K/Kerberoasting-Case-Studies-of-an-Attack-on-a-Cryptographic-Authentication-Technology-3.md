---
layout: default
title: Kerberoasting Case Studies
parent: § Kerberoasting - Case Studies of an Attack on a Cryptographic Authentication Technology 
grand_parent: K
nav_order: 30 
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

## Kerberoasting Case Studies
In recent years, the use of Kerberoasting has been documented as one of the TTPs in reports analyzing the attack modus operandi of particular eCrime groups or their attacks. Kerberoasting is not the sole focus in the following case studies, however it is a critical aspect of each case. The impact of having Kerberoasting in each adversary’s arsenal was significant enough in the following cases to have all been included in MITRE ATT&CK’s procedure examples for Kerberoasting (Praetorian, 2022).

### *Operation Wocao*
The first case is from Fox-IT, a cyber security group providing different incident response services to their clients, such as crisis management, technical investigations, and remediation. In 2019, they published a report of a profile they had built over two years about a Chinese-based hacking group whom they refer to as Operation Wocao. They found that little was known about Wocao. Thus, Fox-IT sought collaboration across the public sector to help determine, with medium confidence, that the techniques and tools they were encountering were being used by Wocao, also known as APT20 within the industry. Fox-IT made the following two determinations. First, in order to execute code on the system being attacked, Wocao used PowerSploit’s Invoke Mimikatz module to try and extract Kerberos tickets from the system’s memory (van Dantzig & Schamper, 2019).

Second, Wocao used PowerSploit’s Invoke-Kerberoast module to try to solicit credentials. Invoke-Kerberoast allows Wocao to request encrypted service tickets by brute forcing Windows service account passwords (Praetorian, 2022; van Dantzig & Schamper, 2019). Both actions aimed to maintain persistence in the system, achieve lateral movement, and eventually escalate privileges. Wocao then used the obtained privileges from the successful Keberoasting-based attacks to exfiltrate data of interest in the system before covering their footprints and cutting access (van Dantzig & Schamper, 2019).

### *Carbon Spider*
The second case is from CrowdStrike, which provides a platform aimed at stopping data breaches to its customers. In 2021, CrowdStrike published a two-part report on Carbon Spider, also known as FIN7, and their use of ransomware. In 2020, Carbon Spider shifted their modus operandi from campaigns focused on companies with point-of-sale devices to using another adversary’s ransomware to launch large attacks with the simple goal of infecting as many victims across all sectors as possible. This type of cyberattack is referred to as Big Game Hunting (BGH). In August 2020, Carbon Spider began using their ransomware, called Darkside. Then, in November 2020, Carbon Spider launched a Darkside ransomware-as-a-service scheme, allowing other bad actors to employ the ransomware while returning a percentage of the ransom obtained back to Carbon Spider. CrowdStrike was able to identify several Darkside campaigns that all utilized similar tools to achieve initial access (Loui & Reynolds, 2021). After gaining this initial access, Carbon Spider’s next step was to harvest credentials and enable lateral movement (Loui & Reynolds, 2021; Praetorian, 2022). In addition to CrackMapExec, Mimikatz, PowerSploit, and SessionGopher, one of the tools consistently used for this task was Kerberoasting. Once in possession of valid credentials, Carbon Spider uses them to move laterally through a compromised system, encrypting files and exfiltrating data to maliciously leak along the way (Loui & Reynolds, 2021).

### *Nobelium*
The third case is based on the Microsoft Threat Intelligence Center (MSTIC) analysis of the attack against SolarWinds by an adversary called Nobelium by MSTIC but known as APT29 or CozyBear within the industry. This attack began in September 2019 and continued periodically until December 2020 (Microsoft 365 Defender Research Team et al., 2021). During this phishing and spear-phishing attack, the adversary began stealing credentials and conducting lateral movements to search for valuable assets through a backdoor they were able to build in the target system. Nobelium was able to maintain long-term persistence and extract vital data from SolarWinds. In addition, they were also able to use SolarWinds’ supply chain to access high-profile victims (Cadieux, 2021). The depth of details unearthed during the investigation earned this attack, called Solarigate, the title of “one of the most sophisticated and protracted intrusion attacks of the decade” (Microsoft 365 Defender Research Team et al., 2021, para. 1).

Microsoft 365 Defender’s telemetry revealed that Nobelium used a vast array of TTPs during Solarigate. These TTPs were carefully curated and implemented for maximum camouflage in SolarWinds’ environment. MSTIC highlighted 16 TTPs used in Solarigate by Nobelium that they found to be the most interesting. Included on this list was Kerberoasting (Microsoft 365 Defender Research Team et al., 2021). Nobelium utilized Kerberoasting to obtain TGS tickets for Active Directory SPNs (Microsoft 365 Defender Research Team et al., 2021; Praetorian, 2022). The actual loss and damage from the Nobelium are not specified, but since they targeted diplomats worldwide, at least one successful attempt may cause unmeasurably devastating consequences.

### *Wizard Spider*
In 2020, Ryuk, ransomware operated by eCrime group Wizard Spider, made a dramatic re-entry into the spotlight when it was used in attacks against Universal Health Service hospitals, managed service providers, and a furniture manufacturer called Steelcase (Hanel, 2019). This campaign of attacks, specifically those targeted at the healthcare sector, was cause for such concern that the Cybersecurity and Infrastructure Security Agency (CISA) issued an alert. This alert identified the Ryuk campaign as an imminent threat to the healthcare and public health sector (CISA et al., 2020). The Digital Forensics and Incident Response (DFIR) Report published full reports on a few of the attacks. The DFIR Report did not specify which attacks they analyzed. However, they provide ample details related to the timeline and TTPs organized according to the MITRE ATT&CK framework (*Ryuk’s Return, 2020; Ryuk Speed Run, 2 Hours to Ransom*, 2020). Therefore, the following two case studies focused on the Ryuk attacks in which Kerberoasting was used. For clarity purposes, the first case discussed is referred to as Email Attack and the second is called Download Attack.

***The email attack.*** The attack took 29 hours to execute. During that time, the adversary successfully employed their ransomware and demanded over 600 Bitcoins, amounting to over six million US dollars at the time. As soon as the payload was executed, the Bazar/Kegtap malware penetrated several processes with the goal of running discovery utilizing Windows built-in utilities (e.g., nltest, netgroup) and a third-party tool called AdFind. After the first wave of discovery on day one, the malware sank to the background only to reemerge the next day to continue discovery. Rubeus was added on the second day so the adversary could attempt Kerberoast to retrieve Advanced Encryption Standard (AES) hashes (Praetorian, 2022; *Ryuk’s Return*, 2020). Shortly after, the adversary began lateral movements. They eventually exfiltrated the AdFind and Rubeus outputs before running additional commands and executing the ransom. As noted in the report, if the first day of recon went unnoticed by a defender, that would leave the defender just over three hours to launch a defense before the ransom was set (*Ryuk’s Return,* 2020).

***The download attack.*** The attack took only two hours, 27 hours less than the Email Attack. The Download Attack was initiated and completed in less time than the defenders would have had to react on day two of the Email Attack. The Download Attack was initiated through a phishing email with malicious links to Google Drive that, when opened, downloaded Bazar malware. Domain discovery began within five minutes, followed by the execution of Cobalt Strike. Once again, AdFind and Rubeus were used to harvest credentials for exfiltration using Kerberoasting techniques. The attack continued until the adversary was able to encrypt the entire domain, at which point they held it for ransom (*Ryuk Speed Run,* 2 Hours to Ransom, 2020).

From the case studies discussed in this paper, it is apparent that bad actors use Kerberoasting attack methods to maintain persistence in the system or escalate privileges in order to achieve various end goals, including data exfiltration, ransomware, and phishing attacks. These case studies all assert that Kerberoasting is a vital part of the attack plan and provides a path to more extensive and more successful attacks. The next sections address ways to detect and mitigate against Kerberoasting attacks.

***

#### Table of Contents
{: .no_toc}

<ul><li> <a href="/docs/K/Kerberoasting-Case-Studies-of-an-Attack-on-a-Cryptographic-Authentication-Technology-1/">Introduction</a></li><li> <a href="/docs/K/Kerberoasting-Case-Studies-of-an-Attack-on-a-Cryptographic-Authentication-Technology-2/">Literature Review</a></li><li> <a href="/docs/K/Kerberoasting-Case-Studies-of-an-Attack-on-a-Cryptographic-Authentication-Technology-3/">Kerberoasting Case Studies</a></li><li> <a href="/docs/K/Kerberoasting-Case-Studies-of-an-Attack-on-a-Cryptographic-Authentication-Technology-4/">Detecting Kerberoasting Attacks</a></li><li> <a href="/docs/K/Kerberoasting-Case-Studies-of-an-Attack-on-a-Cryptographic-Authentication-Technology-5/">Mitigation of Kerberoasting</a></li><li> <a href="/docs/K/Kerberoasting-Case-Studies-of-an-Attack-on-a-Cryptographic-Authentication-Technology-6/">Policy Implications</a></li><li> <a href="/docs/K/Kerberoasting-Case-Studies-of-an-Attack-on-a-Cryptographic-Authentication-Technology-7/">Conclusion</a></li><li> <a href="/docs/K/Kerberoasting-Case-Studies-of-an-Attack-on-a-Cryptographic-Authentication-Technology-8/">References</a></li></ul>

***

</div>
