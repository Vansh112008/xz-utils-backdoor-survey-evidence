
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


## 11. Reichert, B. M., and Obelheiro, R. R. (2024) — Software Supply Chain Security: A Systematic Literature Review

**Reference:** B. M. Reichert and R. R. Obelheiro, “Software supply chain security: a systematic literature review,” *International Journal of Computers and Applications*, vol. 46, no. 10, pp. 853–867, 2024.  
**DOI:** https://doi.org/10.1080/1206212X.2024.2390978  
**Source:** https://www.tandfonline.com/doi/full/10.1080/1206212X.2024.2390978  
**Publication type:** Peer-reviewed journal article / systematic literature review.

**Objective and scope:** The study examines research on software supply chain security, including the security of software development and distribution infrastructure and the risks introduced by external dependencies.

**Method and contribution:** The authors conducted a systematic literature review of research published between 2012 and 2023. Their search covered IEEE Xplore, ACM Digital Library, Engineering Village, Scopus, and arXiv. From 2,051 initially identified studies, 85 were considered relevant.

**Key findings:** The review identifies gaps in research, including limited attention to cloud-related software supply chains, insufficient focus on software distribution, and limited use of threat-modelling frameworks to identify and validate supply-chain threats.

**Relevance to this survey:** This paper provides a research-based foundation for examining the XZ Utils incident as a software supply-chain security failure rather than only a vulnerability in an individual library.

**Limitations:** The review covers literature only up to 2023, so it does not include the XZ Utils incident itself. Its findings provide broader context rather than a direct forensic analysis of CVE-2024-3094.

---

## 12. Ladisa, P., Plate, H., Martinez, M., and Barais, O. (2023) — SoK: Taxonomy of Attacks on Open-Source Software Supply Chains

**Reference:** P. Ladisa, H. Plate, M. Martinez, and O. Barais, “SoK: Taxonomy of Attacks on Open-Source Software Supply Chains,” in *2023 IEEE Symposium on Security and Privacy (SP)*, 2023, pp. 1509–1526.  
**DOI:** https://doi.org/10.1109/SP46215.2023.10179304  
**Source:** https://oaklandsok.github.io/papers/ladisa2023.pdf  
**Publication type:** Peer-reviewed security research conference paper.

**Objective and scope:** The paper develops a structured taxonomy of attacks against open-source software supply chains, covering different stages from code contribution to package distribution.

**Method and contribution:** The authors use a systematisation-of-knowledge approach to classify attack techniques and connect them with documented incidents and possible safeguards. The taxonomy identifies 107 attack vectors associated with 94 real-world incidents and maps them to 33 mitigating safeguards. Surveys involving 17 domain experts and 134 software developers were used to assess the taxonomy.

**Key findings:** Open-source supply chains expose multiple opportunities for malicious code injection. Security measures must therefore address more than source-code vulnerabilities; they must also consider contributors, repositories, build processes, and distribution mechanisms.

**Relevance to this survey:** The taxonomy provides a useful framework for classifying the XZ Utils attack across contributor trust, source repositories, release packaging, build-time execution, and distribution.

**Limitations:** The taxonomy is broad and not designed specifically around the XZ Utils incident. Its safeguards are mapped to attack vectors but are not all experimentally validated as complete prevention mechanisms.

---

## 13. Gu, Y., Ying, L., Pu, Y., Hu, X., Chai, H., Wang, R., Gao, X., and Duan, H. (2023) — Investigating Package Related Security Threats in Software Registries

**Reference:** Y. Gu, L. Ying, Y. Pu, X. Hu, H. Chai, R. Wang, X. Gao, and H. Duan, “Investigating Package Related Security Threats in Software Registries,” in *2023 IEEE Symposium on Security and Privacy (SP)*, 2023.  
**DOI:** https://doi.org/10.1109/SP46215.2023.10179332  
**Source:** https://luneresearch.com/papers/1fb645f5-7b2f-40f5-895c-ce3a32d87abb  
**Publication type:** Peer-reviewed security research conference paper.

**Objective and scope:** The study investigates security weaknesses in software package registries and examines how inconsistencies between registries, mirrors, and package clients can be exploited to distribute malicious software.

**Method and contribution:** The authors systematically analysed six software registry ecosystems and their associated mirrors and clients. They identified 12 potential attack vectors, including six reported for the first time. They developed RScouter, a framework for monitoring registry-related threats, and conducted a one-year measurement study involving six registries and 17 popular mirrors.

**Key findings:** The research examined more than four million packages across 53 million package versions and found security threats in all six ecosystems. Some identified weaknesses had already been exploited by attackers.

**Relevance to this survey:** The study demonstrates that software supply-chain risk extends beyond source-code repositories to package registries and distribution infrastructure. This is relevant when analysing how compromised software can reach downstream users.

**Limitations:** The study focuses on registry ecosystems and package distribution. It does not directly investigate malicious maintainer behaviour or the specific build-time injection technique used in XZ Utils.

---

## 14. Butler, S., et al. (2023) — On Business Adoption and Use of Reproducible Builds for Open and Closed Source Software

**Reference:** S. Butler et al., “On business adoption and use of reproducible builds for open and closed source software,” *Software Quality Journal*, vol. 31, pp. 687–719, 2023.  
**DOI:** https://doi.org/10.1007/s11219-022-09607-z  
**Source:** https://link.springer.com/article/10.1007/s11219-022-09607-z  
**Publication type:** Peer-reviewed journal article.

**Objective and scope:** The study examines how businesses understand, adopt, and use reproducible builds in open-source and closed-source software development.

**Method and contribution:** The authors investigate practitioner and business perspectives through interviews and discussions. The research explores awareness of reproducible builds, technical and organisational barriers, and their practical value in software development.

**Key findings:** Reproducible builds can establish whether a distributed binary corresponds to the source code from which it is claimed to have been produced. The study identifies their value for traceability, collaborative development, and security-related applications. However, adoption remains limited, partly because organisations do not always see a clear business benefit.

**Relevance to this survey:** The XZ Utils incident demonstrated the danger of trusting release artefacts without adequately verifying their relationship to source code. Reproducible builds provide an important potential safeguard against this type of discrepancy.

**Limitations:** The study examines business adoption and practitioner perspectives rather than testing reproducible builds against the XZ Utils backdoor. Its findings also depend partly on the organisations and practitioners represented in the interviews.

---

## 15. Andreoli, A., Lounis, A., Debbabi, M., and Hanna, A. (2023) — On the Prevalence of Software Supply Chain Attacks: Empirical Study and Investigative Framework

**Reference:** A. Andreoli, A. Lounis, M. Debbabi, and A. Hanna, “On the prevalence of software supply chain attacks: Empirical study and investigative framework,” *Forensic Science International: Digital Investigation*, vol. 44, Supplement, article 301508, 2023.  
**DOI:** https://doi.org/10.1016/j.fsidi.2023.301508  
**Source:** https://dfrws.org/wp-content/uploads/2023/03/On_the_prevalence_of_software_supply_chain_attacks_Empirical_study.pdf  
**Publication type:** Peer-reviewed digital forensics research article.

**Objective and scope:** The study examines the characteristics of software supply-chain attacks and proposes an investigative framework for identifying and assessing malicious behaviour in distributed software.

**Method and contribution:** The authors analyse prominent supply-chain attacks and develop an investigative approach for binary analysis. Their framework considers behavioural identification, assessment of malicious intent, and the matching of suspicious behaviours through semantic graphs. The study also examines the historical presence of attack-related behaviours in malware datasets.

**Key findings:** The authors report that behaviours associated with the examined supply-chain attacks had existed in their dataset for approximately 13–21 years before the corresponding attacks. This suggests that some malicious behaviours may be detectable before they are used in major supply-chain incidents.

**Relevance to this survey:** The study supports the importance of behavioural analysis and forensic investigation in identifying malicious software distributed through trusted channels. These ideas are relevant to examining the XZ Utils payload and its concealed execution behaviour.

**Limitations:** The study focuses on selected historical supply-chain attacks and binary behaviour. It predates the XZ Utils incident and does not directly evaluate the specific obfuscation and build-time techniques used in CVE-2024-3094.


