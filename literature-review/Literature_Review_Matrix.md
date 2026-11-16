
# Literature Review Matrix
## Research Topic: XZ Utils Backdoor (2024) – CVE-2024-3094

This matrix documents the literature reviewed for the individual survey project. Sources are classified by publication type to distinguish academic research from technical investigations and industry reports.

---

### Review 1

**Title:** xz Backdoor CVE-2024-3094  
**Authors:** Omkhar Arasaratnam, Bennett Pursell, Harry Toor and Christopher Robinson  
**Year:** 2024  
**Publisher:** Open Source Security Foundation (OpenSSF)  
**Type:** Technical analysis / Security industry report  
**Source:** https://openssf.org/blog/2024/03/30/xz-backdoor-cve-2024-3094/

**Objective:**  
The report explains the discovery, technical scope and software supply-chain implications of the XZ Utils backdoor.

**Approach:**  
The authors examine the compromised XZ Utils releases, the build process through which malicious components were incorporated, and the potential exposure of Linux distributions.

**Key Findings:**  
The report identifies XZ Utils versions 5.6.0 and 5.6.1 as affected releases. It explains that malicious components were concealed in distribution source archives and incorporated into certain package builds. It also highlights the importance of maintainer trust, release procedures and coordination between Linux distributions.

**Relevance to the Present Study:**  
This source provides an important foundation for understanding CVE-2024-3094 and connects the technical compromise with broader open-source supply-chain security concerns.

**Limitations:**  
The report is an incident-focused technical publication rather than a controlled academic study. It does not provide a quantitative evaluation of supply-chain security controls.

---

### Review 2

**Title:** The XZ Utils Backdoor (CVE-2024-3094): Everything You Need to Know, and More  
**Authors:** Christophe Tafani-Dereeper and Katie Knowles  
**Year:** 2024  
**Publisher:** Datadog Security Labs  
**Type:** Technical investigation  
**Source:** https://securitylabs.datadoghq.com/articles/xz-backdoor-cve-2024-3094/

**Objective:**  
The article aims to explain the XZ Utils incident by consolidating the technical findings, attack history and security implications of the compromise.

**Approach:**  
The researchers analyse the available incident evidence and organise technical observations about the malicious package, its discovery and the history of software backdoor attacks.

**Key Findings:**  
The investigation explains how the compromised XZ Utils package affected the liblzma library and how the malicious functionality could interfere with SSH authentication under specific conditions. It also discusses the concealment techniques and the importance of examining the complete software build and distribution process.

**Relevance to the Present Study:**  
This investigation is useful for explaining the attack mechanism and understanding why examining source code alone may not be sufficient to establish the integrity of distributed software.

**Limitations:**  
The article is a technical industry investigation rather than peer-reviewed experimental research. Its main focus is the particular incident rather than a systematic evaluation of defensive controls.

---

### Review 3

**Title:** Wolves in the Repository: A Software Engineering Analysis of the XZ Utils Supply Chain Attack  
**Authors:** Piotr Przymus and Thomas Durieux  
**Year:** 2025  
**Publication:** MSR 2025 Technical Papers  
**Type:** Academic conference research  
**Source:** https://arxiv.org/abs/2504.17473

**Objective:**  
The study investigates how attackers manipulated the software engineering processes of the XZ Utils project to introduce and maintain a backdoor.

**Approach:**  
The authors examine GitHub events and development artefacts to reconstruct the attack timeline and analyse the attacker's activities within the development ecosystem.

**Key Findings:**  
The study highlights that the compromise extended beyond malicious code contributions. Project infrastructure, development practices, community interactions and CI/CD configurations were also relevant to the attack. It demonstrates how legitimate-looking contributions can be used to establish trust and obtain influence over an open-source project.

**Relevance to the Present Study:**  
This research is particularly relevant to the social-engineering and software-governance dimensions of the XZ Utils incident. It supports an analysis of why conventional code-focused security reviews may overlook risks arising from project administration and contributor privileges.

**Limitations:**  
The study focuses on reconstructing one incident. Its findings should not automatically be generalised to every open-source project or development community.

---

### Review 4

**Title:** Investigation of CVE-2024-3094: The XZ Utils Backdoor and Its Averted Network Security Impact  
**Author:** Niko Burkert  
**Year:** 2024  
**Institution:** Institute of Distributed Systems, University of Ulm  
**Type:** University technical research report  
**Source:** https://nurkert.de/pdfs/xz_utils_backdoor.pdf

**Objective:**  
The report investigates the technical operation of the XZ Utils backdoor and evaluates its potential consequences for network security.

**Approach:**  
The author examines XZ Utils, the liblzma library, the vulnerability's technical implementation and the methods used to conceal malicious functionality within the build process.

**Key Findings:**  
The report explains how malicious components were embedded and extracted during package compilation. It discusses the relationship between liblzma and SSH-related system components and demonstrates how a compromised dependency could create an avenue for unauthorised access.

**Relevance to the Present Study:**  
This source provides detailed technical material for explaining the attack chain, build-stage manipulation and the relationship between software dependencies and system security.

**Limitations:**  
The report is primarily a technical investigation of a single vulnerability. It does not establish the effectiveness of security controls through large-scale empirical testing.

---

### Review 5

**Title:** XZ Utils Supply Chain Attack Highlights Pitfalls of Open-Source Software Dependencies  
**Author:** FTI Cybersecurity  
**Year:** 2024  
**Type:** Threat intelligence report  
**Source:** https://fticybersecurity.com/wp-content/uploads/2024/04/DRAFT_FTI-Cybersecurity-Threat-Intelligence-Report-XZ-Utils-Open-Source-Software-Dependencies.pdf

**Objective:**  
The report examines the XZ Utils incident as an example of the security risks associated with open-source dependencies and software supply-chain relationships.

**Approach:**  
The report analyses the attacker's activities, the development history of the compromised project, the insertion of malicious code and the potential consequences for organisations relying on open-source components.

**Key Findings:**  
The report highlights the importance of contributor privileges, dependency visibility and the security of software build processes. It also discusses how trust accumulated through apparently legitimate development contributions can be exploited to compromise a widely used component.

**Relevance to the Present Study:**  
This report helps connect the specific XZ Utils incident with organisational cybersecurity concerns, particularly third-party dependency management, software provenance and supply-chain risk assessment.

**Limitations:**  
The report is an industry threat intelligence publication, not a peer-reviewed academic experiment. Its conclusions should be considered alongside primary technical evidence and academic research.

---

## 6. Andres Freund (2024) — Original disclosure of the XZ Utils backdoor

**Reference:** A. Freund, “backdoor in upstream xz/liblzma leading to ssh server compromise,” oss-security mailing list, March 29, 2024.  
**Source:** https://www.openwall.com/lists/oss-security/2024/03/29/4  
**Publication type:** Primary incident disclosure.

**Review:** This disclosure documents the initial discovery of the XZ Utils compromise. Freund describes unusual CPU consumption during SSH login attempts and errors observed while investigating `liblzma`. The investigation revealed that the upstream XZ repository and release tarballs had been compromised. The disclosure is especially important because it provides first-hand technical evidence of the incident and explains how an unexpected performance anomaly led to the discovery.

**Relevance:** Primary evidence for the attack's discovery, compromised release files, and initial technical investigation.

**Limitations:** This is an incident disclosure rather than a peer-reviewed research paper. It focuses on the discovery and technical findings available at the time of publication.

---

## 7. CVE Program / Red Hat (2024) — CVE-2024-3094 vulnerability record

**Reference:** CVE Program, “CVE-2024-3094: Xz: malicious code in distributed source,” published March 29, 2024.  
**Source:** https://www.cve.org/CVERecord?id=CVE-2024-3094  
**Publication type:** Official vulnerability record.

**Review:** The CVE record formally identifies the malicious code discovered in XZ Utils and describes how the build process extracts a prebuilt object file from a disguised test file. The resulting modified `liblzma` library can affect software linked against it. The record classifies the issue as CWE-506, Embedded Malicious Code, and assigns a CVSS 3.1 score of 10.0, indicating critical severity.

**Relevance:** Provides a standardised vulnerability description, classification, and severity assessment for the case study.

**Limitations:** The record is intended for vulnerability identification and classification. It does not provide a complete investigation of the attacker's activities or evaluate defensive controls.

---

## 8. CERT-EU (2024) — Critical Vulnerability in XZ Utils

**Reference:** CERT-EU, “Critical Vulnerability in XZ Utils,” Security Advisory 2024-032, April 2, 2024.  
**Source:** https://cert.europa.eu/publications/security-advisories/2024-032/  
**Publication type:** Government cybersecurity advisory.

**Review:** This advisory explains the security implications of CVE-2024-3094 and identifies affected Linux distributions. It describes how malicious code interferes with SSH authentication through `systemd`, potentially allowing remote command execution under specific conditions. It also recommends downgrading to an unaffected XZ Utils version and provides information about affected and unaffected distributions.

**Relevance:** Useful for understanding the incident's operational impact, affected environments, and recommended mitigation measures.

**Limitations:** The advisory primarily supports incident response and mitigation. It does not investigate the broader social engineering or contributor-trust aspects of the compromise in depth.

---

## 9. Microsoft (2024) — FAQ and guidance for the XZ Utils backdoor

**Reference:** B. Brekkan, “Microsoft FAQ and guidance for XZ Utils backdoor,” Microsoft Community Hub, April 1, 2024.  
**Source:** https://techcommunity.microsoft.com/blog/microsoftthreatprotectionblog/microsoft-faq-and-guidance-for-xz-utils-backdoor/4101961  
**Publication type:** Industry security analysis and guidance.

**Review:** Microsoft's guidance explains the role of XZ Utils in Linux environments and the implications of the compromise affecting versions 5.6.0 and 5.6.1. It discusses the potential interaction between `liblzma` and OpenSSH, and provides guidance for assessing exposure and responding to the vulnerability. The publication is useful for understanding how organisations can approach vulnerability assessment and incident response when a widely used open-source dependency is compromised.

**Relevance:** Connects the technical incident to enterprise security monitoring, exposure assessment, and mitigation practices.

**Limitations:** The publication is vendor guidance rather than independent academic research. Its recommendations are oriented towards Microsoft's security products and enterprise users.

---

## 10. Red Hat (2024) — CVE-2024-3094 security analysis

**Reference:** Red Hat, “CVE-2024-3094,” Red Hat Customer Portal, 2024.  
**Source:** https://access.redhat.com/security/cve/cve-2024-3094  
**Publication type:** Vendor security advisory and vulnerability analysis.

**Review:** Red Hat describes how malicious code was inserted into XZ Utils release tarballs beginning with version 5.6.0. Its analysis explains that the build process extracts a prebuilt object file from a disguised test file and uses it to modify functions in `liblzma`. The advisory also distinguishes between affected community distributions and Red Hat Enterprise Linux products that were not affected. This illustrates why vulnerability assessment must consider the exact software distribution, package version, and build process rather than relying only on the upstream project name.

**Relevance:** Provides technical details about the build-time injection mechanism and demonstrates the importance of distribution-specific vulnerability assessment.

**Limitations:** The analysis focuses on Red Hat's products and ecosystem. It is not a comparative study of all Linux distributions or a peer-reviewed evaluation of software supply-chain security.

## Review Progress

| Review | Source | Status |
|---|---|---|
| 1 | OpenSSF (2024) | Reviewed |
| 2 | Datadog Security Labs (2024) | Reviewed |
| 3 | Przymus and Durieux (2025) | Reviewed |
| 4 | Burkert (2024) | Reviewed |
| 5 | FTI Cybersecurity (2024) | Reviewed |

**Target: 25 individually reviewed sources.**

