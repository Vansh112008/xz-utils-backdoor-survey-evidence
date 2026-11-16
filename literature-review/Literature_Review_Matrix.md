
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

## 4. Chandramouli, R., Kautz, F., and Torres-Arias, S. (2024) — Strategies for the Integration of Software Supply Chain Security in DevSecOps CI/CD Pipelines

**Reference:** R. Chandramouli, F. Kautz, and S. Torres-Arias, *Strategies for the Integration of Software Supply Chain Security in DevSecOps CI/CD Pipelines*, NIST SP 800-204D, Feb. 12, 2024.  
**DOI:** https://doi.org/10.6028/NIST.SP.800-204D  
**Publication type:** Government technical standard / guidance.

**Objective and scope:** The publication provides practical strategies for integrating software supply-chain security controls into DevSecOps continuous integration and continuous delivery (CI/CD) pipelines.

**Method and contribution:** NIST organises security assurance activities around software production stages such as build, test, package and deployment, and maps the strategies to the Secure Software Development Framework.

**Key findings and contribution:** The guidance treats supply-chain integrity as a lifecycle concern and identifies controls relating to artifacts, attestations, repositories, provenance and software bills of materials.

**Relevance to this survey:** It provides an authoritative control framework for the build and delivery risks highlighted by the XZ Utils incident.

**Limitations:** It is guidance rather than an empirical evaluation of the XZ attack or a proof that implementing the listed controls prevents every compromise.
---

## 5. Yu, S., Song, W., Hu, X., and Yin, H. (2024) — On the Correctness of Metadata-Based SBOM Generation: A Differential Analysis Approach

**Reference:** S. Yu, W. Song, X. Hu, and H. Yin, “On the correctness of metadata-based SBOM generation: A differential analysis approach,” in *Proc. 54th Annual IEEE/IFIP International Conference on Dependable Systems and Networks*, 2024.  
**DOI:** https://doi.org/10.1109/DSN58291.2024.00018  
**Publication type:** Peer-reviewed conference paper.

**Objective and scope:** The study evaluates whether commonly used software bill of materials (SBOM) generators accurately represent software components and dependencies.

**Method and contribution:** The authors perform differential analysis across four SBOM-generation tools and compare their output for dependency omissions and inconsistencies.

**Key findings:** The evaluation reports inconsistent SBOMs and missing dependencies across the evaluated tools. The authors also describe a parser-confusion attack that can conceal components in generated inventories.

**Relevance to this survey:** The work shows that an SBOM is useful only when its component inventory is sufficiently accurate. This matters when organisations need to identify exposure to a compromised dependency such as XZ Utils.

**Limitations:** The study evaluates metadata-based SBOM generation, not malicious maintainer behaviour or the full XZ attack chain.
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

## 9. Schueller, W., and Wachs, J. (2024) — Modeling Interconnected Social and Technical Risks in Open Source Software Ecosystems

**Reference:** W. Schueller and J. Wachs, “Modeling interconnected social and technical risks in open source software ecosystems,” *Big Data & Society*, 2024.  
**DOI:** https://doi.org/10.1177/26339137241231912  
**Publication type:** Peer-reviewed journal research article.

**Objective and scope:** The paper studies how social and technical risks interact in open-source ecosystems, including the concentration of maintenance responsibilities and dependency relationships.

**Method and contribution:** The authors present a methodological framework that models ecosystem risk using both software dependencies and the developers who maintain interconnected libraries.

**Key findings:** The work argues that technical dependency risks and social factors such as maintainer concentration should be examined together rather than as separate problems.

**Relevance to this survey:** The XZ Utils incident illustrates why project governance, maintainer workload and contributor trust can be as important as code-level controls.

**Limitations:** The paper develops a general ecosystem risk framework; it is not a forensic reconstruction of CVE-2024-3094.
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

## 15. Lins, M., Mayrhofer, R., Roland, M., Hofer, D., and Schwaighofer, M. (2024) — On the Critical Path to Implant Backdoors and the Effectiveness of Potential Mitigation Techniques: Early Learnings from XZ

**Reference:** M. Lins, R. Mayrhofer, M. Roland, D. Hofer, and M. Schwaighofer, “On the critical path to implant backdoors and the effectiveness of potential mitigation techniques: Early learnings from XZ,” arXiv:2404.08987, Apr. 13, 2024.  
**Source:** https://arxiv.org/abs/2404.08987  
**Publication type:** Research preprint (arXiv); do not describe as peer-reviewed conference proceedings unless a later peer-reviewed version is separately cited.

**Objective and scope:** The paper analyses the XZ backdoor attack path and discusses possible mitigation techniques at different stages of the software supply chain.

**Method and contribution:** The authors organise publicly available incident information into an attack path and examine potential defensive measures that could interrupt or expose the attack.

**Key findings:** The work emphasises that the compromise involved multiple stages, from social engineering and contributor trust to build-time injection and downstream execution.

**Relevance to this survey:** It is directly incident-specific and supports the lifecycle-based analysis of preventive and detective controls.

**Limitations:** It is an early research preprint based on information available shortly after discovery; its claims should be distinguished from later peer-reviewed analysis.
## 16. Amft, S., Höltervennhoff, S., Panskus, R., Marky, K., and Fahl, S. (2024) — Everyone for Themselves? A Qualitative Study about Individual Security Setups of Open Source Software Contributors

**Reference:** S. Amft, S. Höltervennhoff, R. Panskus, K. Marky, and S. Fahl, “Everyone for Themselves? A Qualitative Study about Individual Security Setups of Open Source Software Contributors,” in *2024 IEEE Symposium on Security and Privacy (SP)*, 2024.  
**Source:** https://cispa.de/en/research/publications/79233-everyone-for-themselves-a-qualitative-study-about-individual-security-setups-of-open-source-software-contributors  
**Publication type:** Peer-reviewed security research conference paper.

**Objective and scope:** The study investigates how open-source software contributors secure their personal development environments, including repository credentials, code-signing keys, and systems used to develop and distribute software.

**Method and contribution:** The researchers conducted 20 semi-structured interviews with experienced contributors to critical open-source projects. The study examines their security practices, motivations, decision-making, and experiences.

**Key findings:** Contributors generally show an interest in security, but security practices are rarely discussed or formally enforced within open-source communities. Social factors such as trust, respect, and politeness can discourage contributors from questioning practices or sharing security concerns.

**Relevance to this survey:** The XZ Utils incident involved a long-term compromise of trust within an open-source project. This study helps explain why contributor security, informal relationships, and community practices should be considered part of software supply-chain defence.

**Limitations:** The study is based on qualitative interviews and does not establish that the same social factors caused the XZ Utils compromise. Its findings should not be treated as a direct investigation of that incident.

---

## 17. Wermke, D., Klemmer, J. H., Wöhler, N., Schmüser, J., Ramulu, H. S., Acar, Y., and Fahl, S. (2023) — Always Contribute Back: A Qualitative Study on Security Challenges of the Open Source Supply Chain

**Reference:** D. Wermke, J. H. Klemmer, N. Wöhler, J. Schmüser, H. S. Ramulu, Y. Acar, and S. Fahl, “‘Always Contribute Back’: A Qualitative Study on Security Challenges of the Open Source Supply Chain,” in *2023 IEEE Symposium on Security and Privacy (SP)*, 2023.  
**Source:** https://s3c2.org/research/  
**Publication type:** Peer-reviewed security research conference paper.

**Objective and scope:** The research examines how developers and organisations use open-source components and the security challenges they face when incorporating external software into their projects.

**Method and contribution:** The study uses qualitative interviews with 25 software developers, architects, and engineers from industry software projects. It explores organisational practices, policies, and challenges related to the use of external open-source code.

**Key findings:** Open-source components play an important role in many software projects. Although organisations often have policies or recommended practices for incorporating external code, developers frequently need more resources and support to audit the components they use.

**Relevance to this survey:** The XZ Utils incident demonstrates how trust in an upstream open-source component can create downstream risk. This study helps explain the challenges organisations face when assessing the security and reliability of external dependencies.

**Limitations:** The study focuses on developer and organisational experiences rather than analysing a specific malicious software incident. Its qualitative findings do not quantify the probability of a supply-chain compromise.

---

## 18. Muralee, S., Koishybayev, I., Nahapetyan, A., Tystahl, G., Reaves, B., Bianchi, A., Enck, W., Kapravelos, A., and Machiry, A. (2023) — ARGUS: A Framework for Staged Static Taint Analysis of GitHub Workflows and Actions

**Reference:** S. Muralee, I. Koishybayev, A. Nahapetyan, G. Tystahl, B. Reaves, A. Bianchi, W. Enck, A. Kapravelos, and A. Machiry, “ARGUS: A Framework for Staged Static Taint Analysis of GitHub Workflows and Actions,” in *32nd USENIX Security Symposium*, 2023.  
**Source:** https://www.usenix.org/conference/usenixsecurity23/presentation/muralee  
**Publication type:** Peer-reviewed systems security conference paper.

**Objective and scope:** The paper examines security risks in GitHub Actions and automated CI/CD workflows, which are commonly used to build, test, and distribute software.

**Method and contribution:** The researchers introduce ARGUS, a framework that performs staged static taint analysis of GitHub workflows and actions. The framework examines how potentially untrusted data can flow through workflow components and affect security-sensitive operations.

**Key findings:** Automated development workflows can introduce security weaknesses when untrusted inputs interact with privileged operations. Static analysis can help identify potentially dangerous data flows before they are exploited.

**Relevance to this survey:** The XZ Utils compromise involved a malicious build process that inserted code into a distributed software artefact. ARGUS provides a relevant perspective on the security of automated development and build infrastructure.

**Limitations:** The paper focuses on GitHub workflow and action security. It does not directly detect or prevent the particular obfuscation and build-time injection methods used in CVE-2024-3094.

---

## 19. Nahum, M., Grolman, E., Maimon, I., Mimran, D., Brodt, O., Elyashar, A., Elovici, Y., and Shabtai, A. (2024) — OSSIntegrity: Collaborative Open-Source Code Integrity Verification

**Reference:** M. Nahum, E. Grolman, I. Maimon, D. Mimran, O. Brodt, A. Elyashar, Y. Elovici, and A. Shabtai, “OSSIntegrity: Collaborative open-source code integrity verification,” *Computers & Security*, vol. 144, article 103977, 2024.  
**DOI:** https://doi.org/10.1016/j.cose.2024.103977  
**Source:** https://www.sciencedirect.com/science/article/pii/S0167404824002827  
**Publication type:** Peer-reviewed journal research article.

**Objective and scope:** The study addresses targeted attacks against open-source software libraries and proposes a collaborative method for verifying code integrity before software is packaged and deployed.

**Method and contribution:** The authors introduce OSSIntegrity, a crowdsourced and distributed code-verification framework. It integrates verification into the software build process and compares the package code against the consensus established by independent verifiers.

**Key findings:** The framework aims to identify inconsistencies that may indicate unauthorised code modifications. The authors report an evaluation involving 127,000 files, with an average alert-generation time of approximately 26 seconds against the attacks considered in their evaluation.

**Relevance to this survey:** The framework is relevant to the XZ Utils incident because it addresses the problem of trusting externally maintained software without independently checking code integrity. Collaborative verification could provide an additional safeguard against unauthorised modifications.

**Limitations:** The framework's evaluation does not establish that it would necessarily have detected the XZ Utils backdoor. Its effectiveness depends on the verification process, participating verifiers, and the attack scenarios considered.

---

## 20. Rebatchi, H., Moha, N., and Bissyandé, T. F. (2024) — Dependabot and Security Pull Requests: Large Empirical Study

**Reference:** H. Rebatchi, N. Moha, and T. F. Bissyandé, “Dependabot and security pull requests: large empirical study,” *Empirical Software Engineering*, vol. 29, no. 5, 2024.  
**DOI:** https://doi.org/10.1007/s10664-024-10523-y  
**Source:** https://hdl.handle.net/10993/62972  
**Publication type:** Peer-reviewed journal research article.

**Objective and scope:** The study investigates how automated dependency-management tools, particularly Dependabot, contribute to the identification and remediation of vulnerabilities in open-source software projects.

**Method and contribution:** The authors conduct a large empirical investigation of security-related pull requests and dependency-update practices. The study examines how projects respond to automated dependency alerts and the role of these updates in software maintenance.

**Key findings:** The research highlights the importance of dependency maintenance in reducing software security risks. Automated tools can help developers identify and address vulnerable dependencies, although their effectiveness depends on project response and the adoption of recommended updates.

**Relevance to this survey:** The XZ Utils incident illustrates that dependency security cannot be reduced to checking whether a known vulnerability exists. Nevertheless, automated dependency monitoring remains an important component of a broader supply-chain security strategy.

**Limitations:** Dependency-update automation primarily addresses known vulnerabilities and outdated packages. It cannot independently establish that a trusted maintainer or a newly released package is free from intentionally malicious code.

## 21. Benedetti, G., Solarin, O., Miller, C., Tystahl, G., Enck, W., Kästner, C., Kapravelos, A., Merlo, A., and Verderame, L. (2025) — An Empirical Study on Reproducible Packaging in Open-Source Ecosystems

**Reference:** G. Benedetti, O. Solarin, C. Miller, G. Tystahl, W. Enck, C. Kästner, A. Kapravelos, A. Merlo, and L. Verderame, “An Empirical Study on Reproducible Packaging in Open-Source Ecosystems,” in *2025 IEEE/ACM 47th International Conference on Software Engineering (ICSE)*, 2025.  
**DOI:** https://doi.org/10.1109/ICSE55347.2025.00136  
**Source:** https://doi.org/10.1109/ICSE55347.2025.00136  
**Publication type:** Peer-reviewed software engineering conference paper.

**Objective and scope:** The study investigates whether software packages distributed through popular open-source ecosystems can be reproduced independently from their source code, helping establish confidence in the integrity of published software artefacts.

**Method and contribution:** The authors conduct a quantitative study of 4,000 packages in each of six ecosystems: npm, Maven, PyPI, Go, RubyGems, and Cargo. They examine the reproducibility of package builds and investigate technical and configuration-related barriers.

**Key findings:** Reproducibility rates vary substantially across ecosystems. The authors find that relatively straightforward infrastructure configuration and build-tool changes can substantially improve reproducibility across the ecosystems studied.

**Relevance to this survey:** The XZ Utils attack exploited the gap between source repositories and distributed release artefacts. Reproducible packaging is directly relevant because independent rebuilding can help verify whether a distributed package corresponds to its claimed source.

**Limitations:** The study evaluates package reproducibility rather than the detection of every form of malicious source-code contribution. Reproducible builds alone cannot establish that the source code itself is trustworthy.

---

## 22. Sammak, R., Rotthaler, A. L., Ramulu, H. S., Wermke, D., and Acar, Y. (2024) — Developers’ Approaches to Software Supply Chain Security: An Interview Study

**Reference:** R. Sammak, A. L. Rotthaler, H. S. Ramulu, D. Wermke, and Y. Acar, “Developers’ approaches to software supply chain security: An interview study,” in *Proc. 2024 Workshop on Software Supply Chain Offensive Research and Ecosystem Defenses (SCORED ’24)*, Oct. 14–18, 2024.  
**DOI:** https://doi.org/10.1145/3689944.3696160  
**Publication type:** Peer-reviewed research workshop paper.

**Objective and scope:** The study investigates how developers understand and practise software supply-chain security in their work.

**Method and contribution:** The authors use an interview-based approach to explore developers’ security practices, experiences and challenges.

**Key findings:** The study provides qualitative evidence about how security responsibilities, awareness and practical constraints influence software supply-chain practices.

**Relevance to this survey:** It complements technical analyses by examining how developer decisions and organisational practices affect the security of software production.

**Limitations:** Interview findings provide contextual and qualitative insight; they do not directly measure the effectiveness of a specific technical mitigation for CVE-2024-3094.
---

## 23. Nocera, S., Vegas, S., Scanniello, G., and Juristo, N. (2025) — Software Composition Analysis and Supply Chain Security in Apache Projects: An Empirical Study

**Reference:** S. Nocera, S. Vegas, G. Scanniello, and N. Juristo, “Software Composition Analysis and Supply Chain Security in Apache Projects: An Empirical Study,” in *2025 IEEE/ACM 22nd International Conference on Mining Software Repositories (MSR)*, 2025, pp. 103–115.  
**DOI:** https://doi.org/10.1109/MSR66628.2025.00027  
**Source:** https://ieeexplore.ieee.org/abstract/document/11025577  
**Publication type:** Peer-reviewed software engineering conference paper.

**Objective and scope:** The study investigates whether adopting Software Composition Analysis (SCA) tools can improve the security of software supply chains in open-source projects.

**Method and contribution:** The authors use a cohort-based empirical design to analyse open-source Java Maven projects maintained by the Apache Software Foundation and hosted on GitHub. They investigate the use of OWASP Dependency-Check and examine changes in the vulnerabilities associated with project dependencies over time.

**Key findings:** The results indicate that adopting SCA appears to reduce the overall number and severity of vulnerabilities, including high-severity vulnerabilities. The study also observes an increase in the identification of low-severity vulnerabilities.

**Relevance to this survey:** SCA tools can help organisations identify vulnerable dependencies and improve software component visibility. However, the XZ Utils incident illustrates an important limitation: identifying known vulnerabilities in dependencies is not equivalent to verifying that a newly released dependency is free of deliberately malicious code.

**Limitations:** The study focuses on Apache Java Maven projects and known dependency vulnerabilities. It does not directly evaluate the detection of malicious maintainer activity or hidden build-time backdoors.

---

## 24. Fröh, F. N., Gobbi, M. F., and Kinder, J. (2023) — Differential Static Analysis for Detecting Malicious Updates to Open Source Packages

**Reference:** F. N. Fröh, M. F. Gobbi, and J. Kinder, “Differential Static Analysis for Detecting Malicious Updates to Open Source Packages,” in *Proceedings of the 2023 Workshop on Software Supply Chain Offensive Research and Ecosystem Defenses (SCORED '23)*, 2023, pp. 41–49.  
**DOI:** https://doi.org/10.1145/3605770.3625211  
**Source:** https://doi.org/10.1145/3605770.3625211  
**Publication type:** Research workshop paper.

**Objective and scope:** The paper addresses the risk of malicious code being introduced into widely used open-source packages through software updates.

**Method and contribution:** The author proposes an approach based on differential static analysis. Rather than examining a package release in isolation, the approach compares successive package versions to identify suspicious code modifications.

**Key findings:** The work highlights that malicious package updates can affect many downstream applications because package managers automatically distribute updates through dependency trees. Comparing versions can help identify potentially malicious modifications that deserve further investigation.

**Relevance to this survey:** The XZ Utils backdoor was introduced through compromised releases of a trusted project. Differential analysis provides a relevant defensive approach for identifying unusual changes between software versions.

**Limitations:** Static comparison can identify suspicious modifications but cannot reliably determine malicious intent in every case. Legitimate updates may also contain substantial code changes, while obfuscated or indirect malicious behaviour may be difficult to identify.

---

## 25. Shen, Y., Gao, X., Sun, H., and Guo, Y. (2025) — Understanding Vulnerabilities in Software Supply Chains

**Reference:** Y. Shen, X. Gao, H. Sun, and Y. Guo, “Understanding vulnerabilities in software supply chains,” *Empirical Software Engineering*, vol. 30, article 20, 2025.  
**DOI:** https://doi.org/10.1007/s10664-024-10581-2  
**Source:** https://link.springer.com/article/10.1007/s10664-024-10581-2  
**Publication type:** Peer-reviewed journal research article.

**Objective and scope:** The study investigates how vulnerabilities originate in software supply chains, propagate through dependencies, can be localised, and are eventually repaired by software developers.

**Method and contribution:** The authors examine 10,000 popular Java Maven artefacts and construct a detailed vulnerability dataset involving 50 libraries and 61 CVEs. They also analyse 1,280 client projects and develop a finer-grained method-level approach to assess whether vulnerabilities actually propagate into dependent applications.

**Key findings:** The authors report that 99% of vulnerabilities identified in client programs originate from dependencies. They also find that 81.26% of vulnerabilities detected through package-level propagation analysis are false positives. The study highlights the importance of examining actual code-level usage rather than relying exclusively on package-level dependency relationships.

**Relevance to this survey:** The research demonstrates the complexity of downstream risk assessment in software supply chains. It supports the need for accurate dependency analysis, vulnerability localisation, and coordinated remediation when a widely used component is compromised.

**Limitations:** The study focuses on vulnerabilities in Java Maven projects rather than intentional backdoors. Its findings therefore provide context for dependency-risk analysis but do not directly evaluate the XZ Utils attack.


