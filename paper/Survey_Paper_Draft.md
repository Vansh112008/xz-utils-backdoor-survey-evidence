
# XZ Utils Backdoor (2024): A Survey of Open-Source Software Supply-Chain Security

**Student:** Vansh  
**URN:** 2581375  
**Programme:** B.Tech Computer Science and Engineering  
**Semester:** 3  
**Batch:** 3F  
**Course:** Foundations of Cybersecurity  
**Course Code:** CSE25305  
**Faculty:** Dr. Abhishek Pandey  
**Submission Date:** 15 November 2026  

---

# 1. Introduction

## 1.1 Background

Open-source software has become a fundamental component of modern computing infrastructure. Operating systems, enterprise applications, cloud platforms, development tools, and network services frequently depend on software libraries and utilities maintained by distributed communities.

The open-source development model offers several advantages, including transparency, collaborative development, flexibility, and reduced development costs. However, it also creates security challenges because software projects may depend on external contributors, third-party libraries, automated build systems, and package repositories.

A compromise at any stage of this ecosystem can affect downstream users and organisations. Such attacks are generally described as software supply-chain attacks.

The XZ Utils backdoor incident of March 2024 is a significant example of this threat [1]–[6], [10], [24]. XZ Utils is a data-compression utility used in many Linux-based environments. Its library, liblzma, is used by numerous software components.

The incident involved malicious modifications to the XZ Utils project that were introduced through its development and release process [1], [5], [6], [10], [24]. The malicious functionality was designed to interfere with OpenSSH authentication in certain affected Linux environments.

The discovery of the backdoor demonstrated that even widely trusted open-source projects can become targets of sophisticated and persistent attacks [7], [8], [20], [21], [25].

## 1.2 Problem Statement

Traditional software security approaches frequently focus on identifying vulnerabilities within application source code. However, the XZ Utils incident demonstrated that software security also depends on the integrity of contributors, repositories, build systems, release packages, and distribution mechanisms.

A malicious modification may remain difficult to detect when it is introduced gradually and concealed within otherwise legitimate development activity.

This creates a need to examine software supply-chain security as a broader discipline and identify methods for preventing, detecting, and responding to attacks involving trusted open-source components [7], [14], [21], [23].

## 1.3 Research Objectives

The main objectives of this survey are:

1. To examine the technical background and development of the XZ Utils backdoor incident.
2. To understand the major stages and techniques involved in open-source software supply-chain attacks.
3. To review existing research on contributor security, dependency management, build integrity, and malicious code detection.
4. To compare preventive and detective security approaches relevant to software supply chains.
5. To identify research gaps and recommend security practices that can improve open-source software integrity.

## 1.4 Research Questions

This survey addresses the following research questions:

- RQ1: How did the XZ Utils backdoor exploit weaknesses in the open-source software development and release process?
- RQ2: What security risks affect open-source software supply chains?
- RQ3: What approaches are available to detect and prevent malicious modifications in software dependencies and build pipelines?
- RQ4: What limitations exist in current software supply-chain security practices?
- RQ5: What measures can improve the long-term security and resilience of open-source projects?

## 1.5 Scope of the Survey

The survey focuses on the XZ Utils backdoor as a case study of open-source software supply-chain compromise. It also considers broader research concerning malicious package updates, contributor trust, secure build systems, reproducible builds, software provenance, and dependency vulnerability management.

The study uses academic publications, technical investigations, vulnerability advisories, and institutional security reports. It distinguishes between peer-reviewed research and other technical sources when discussing evidence and conclusions.

---

# 2. Background of the XZ Utils Incident

## 2.1 Overview of XZ Utils

XZ Utils is an open-source data-compression utility that provides tools and libraries for compressing and decompressing files. Its functionality is used in several Linux distributions and software environments.

The liblzma library is an important component of the XZ Utils ecosystem. Software applications may depend on this library directly or indirectly.

Because widely distributed software components can have extensive dependency relationships, compromising a trusted library may create security consequences beyond the original project.

## 2.2 Discovery of the Backdoor

The backdoor was publicly identified in March 2024 by Andres Freund, who noticed unusual performance behaviour during testing involving SSH connections [1], [5], [6].

Further investigation identified malicious code associated with XZ Utils versions 5.6.0 and 5.6.1 [2]–[6]. The affected release process included manipulated build-related components that enabled malicious functionality to be introduced into distributed packages.

The discovery prevented a potentially serious compromise from spreading more widely across affected systems.

## 2.3 Attack Mechanism

The incident involved several interconnected stages [1], [3]–[6], [10], [24]:

1. Malicious changes were introduced into the XZ Utils project.
2. Release-related build components were manipulated.
3. Malicious functionality was concealed within the distribution process.
4. In affected environments, the resulting library could interfere with OpenSSH authentication.
5. The resulting behaviour created a potential pathway for unauthorised access under specific conditions.

The attack illustrates why inspecting only the visible source-code repository may not be sufficient to establish the integrity of a distributed software package.

## 2.4 Security Impact

The incident created a critical risk for systems using affected XZ Utils packages in vulnerable configurations.

However, it is important to distinguish between potential impact and confirmed exploitation. The discovery occurred before the malicious releases became widely deployed across stable production systems.

The event nevertheless demonstrated that a compromise involving a trusted open-source dependency can have consequences for operating-system security, software distribution, and organisational trust.

## 2.5 Lessons from the Incident

The incident highlighted several important lessons [7], [8], [11], [14], [20], [25]:

- Open-source projects require sustainable maintainer security practices.
- Contributor trust must be supported by independent review and governance.
- Release packages should be independently verified.
- Build systems must be treated as security-critical infrastructure.
- Dependency monitoring should include unexpected or suspicious changes.
- Security research must consider both technical and organisational attack surfaces.

---

# 3. Software Supply-Chain Security

## 3.1 Concept and Definition

A software supply chain consists of the people, processes, tools, dependencies, and infrastructure involved in developing, building, distributing, and maintaining software.

Software supply-chain security aims to protect the integrity, authenticity, and reliability of these interconnected components.

Unlike conventional application security, which often focuses on vulnerabilities in software functionality, supply-chain security examines the entire lifecycle through which software is produced and delivered.

## 3.2 Major Categories of Supply-Chain Attacks

Software supply-chain attacks can occur at multiple stages [7], [14], [21], [23]:

### 3.2.1 Source-Code Attacks

These attacks involve unauthorised or malicious modifications to software source code. Examples include malicious code injection, compromised commits, and unauthorised changes to project repositories.

### 3.2.2 Contributor and Account Attacks

Attackers may compromise legitimate developer accounts or gradually establish influence within an open-source project. Such attacks exploit weaknesses in authentication, contributor verification, and project governance.

### 3.2.3 Build-System Attacks

Build infrastructure can be manipulated to introduce malicious functionality during compilation or packaging. This is particularly dangerous when distributed binaries differ from the source code reviewed by maintainers.

### 3.2.4 Package-Distribution Attacks

These attacks involve tampering with software packages, release archives, repositories, or distribution infrastructure.

### 3.2.5 Dependency Attacks

Modern applications rely on third-party libraries. Attackers may exploit dependency relationships through malicious packages, compromised updates, or dependency confusion.

## 3.3 Relevance to XZ Utils

The XZ Utils incident demonstrates the interaction between contributor trust, source-code changes, build processes, and software distribution.

It highlights that supply-chain attacks can exploit legitimate development workflows rather than relying exclusively on traditional technical vulnerabilities.

The attack therefore provides a useful case study for understanding why security controls must be applied across the entire software lifecycle.

---

# 4. Literature Review Methodology

## 4.1 Literature Identification

The literature review examines publications and technical investigations related to the XZ Utils incident and broader open-source software supply-chain security.

The search strategy uses terms relating to software supply-chain attacks, malicious package updates, contributor security, reproducible builds, software provenance, dependency vulnerabilities, and CI/CD security.

Sources include academic publications, institutional advisories, technical investigations, and industry security reports.

## 4.2 Inclusion and Exclusion Criteria

Sources were considered for inclusion when they addressed the research questions, provided relevant technical or empirical findings, or contributed to understanding open-source software supply-chain security.

Duplicate publications, unrelated materials, and sources lacking sufficient identification details were excluded.

## 4.3 Thematic Classification

The selected literature is organised into five major themes:

1. Open-source software supply-chain security.
2. Contributor trust and project governance.
3. Build-system and release integrity.
4. Vulnerability detection and dependency analysis.
5. Reproducible builds and software provenance.

The thematic classification supports comparison between incident-specific investigations and broader research findings.

## 4.4 Selection Process

The literature selection process is illustrated in Figure 1. The final numerical counts of identified, screened, excluded, and included records will be reported after the search log has been verified.

---

# 5. Comparative Analysis of Existing Security Approaches

## 5.1 Static Analysis

Static analysis examines software code without executing it. It can help identify suspicious code patterns, unsafe operations, and potentially malicious modifications.

However, static analysis may have limitations when malicious functionality is deliberately concealed or introduced through complex build processes.

## 5.2 Dynamic Analysis

Dynamic analysis evaluates software behaviour during execution. It can help identify unusual network activity, unexpected process behaviour, and suspicious interactions with system components.

Its effectiveness depends on the quality of test environments, execution coverage, and the ability to reproduce the relevant conditions.

## 5.3 Software Composition Analysis

Software Composition Analysis (SCA) identifies third-party dependencies and checks them against known vulnerability information.

SCA is useful for dependency visibility and vulnerability management. However, detecting known vulnerabilities does not necessarily identify newly introduced malicious functionality in a trusted package.

## 5.4 Reproducible Builds

Reproducible builds aim to ensure that independently performed builds from the same source and build instructions produce equivalent outputs.

This approach can strengthen confidence in software packages by making unexplained differences easier to identify.

## 5.5 Software Provenance and SBOMs

Software provenance records information about the origin and production of software artifacts. A Software Bill of Materials (SBOM) provides an inventory of software components and dependencies.

These approaches improve transparency and support dependency management, incident response, and risk assessment.

However, an SBOM alone cannot prove that every listed component is trustworthy or free from malicious modifications.

## 5.6 Comparative Summary

The security approaches discussed above address different parts of the software supply chain. No single method provides complete protection.

An effective strategy combines code analysis, runtime monitoring, dependency inventories, build verification, provenance, and independent review.

---

# 6. Security Recommendations

The XZ Utils incident supports a defence-in-depth approach to open-source software security.

Recommended practices include:

1. Enforce multi-factor authentication for maintainers and release administrators.
2. Require independent review for security-sensitive code changes.
3. Protect release credentials and signing keys.
4. Use reproducible builds wherever feasible.
5. Verify package signatures and provenance.
6. Maintain accurate software dependency inventories.
7. Monitor unusual contributor and repository activity.
8. Apply static and dynamic analysis to critical software components.
9. Secure automated build and deployment pipelines.
10. Establish incident-response and vulnerability-disclosure procedures.

These practices should be adapted to the resources and risk profiles of individual projects.

---

# 7. Research Gaps and Future Directions

The reviewed literature highlights several areas requiring further investigation.

## 7.1 Malicious Contributor Detection

Future research should examine methods for detecting suspicious contributor behaviour while avoiding unfair assumptions about legitimate contributors.

## 7.2 Build-Process Transparency

More effective approaches are needed to verify that distributed software packages accurately correspond to reviewed source code and approved build instructions.

## 7.3 Security Support for Small Projects

Many open-source projects have limited resources. Research should explore affordable and accessible security practices for smaller maintainer teams.

## 7.4 Detection of Novel Supply-Chain Attacks

Existing vulnerability databases and scanning tools may not identify previously unknown malicious functionality. More research is needed into behavioural detection and anomaly analysis.

## 7.5 Sustainable Open-Source Governance

Future studies should investigate maintainer workload, contributor trust, governance structures, and the long-term sustainability of security practices.

---

# 8. Classification of Reviewed Literature

The reviewed literature consists of academic research, incident investigations, institutional advisories, and industry reports [3]–[9], [14], [21], [25]. These source categories contribute different forms of evidence to the understanding of software supply-chain security.

**Table 1. Classification of literature reviewed**

| Literature category | Main focus | Contribution to this survey | Evidence limitations |
|---|---|---|---|
| Incident-specific investigations | XZ Utils backdoor and CVE-2024-3094 | Explain the attack, discovery, and technical implications | Primarily focused on one incident |
| Academic research | Software supply-chain security | Provides research frameworks, empirical findings, and theoretical perspectives | May not directly examine the XZ incident |
| Institutional security advisories | Vulnerability details and mitigation | Provide authoritative technical guidance and affected-version information | Usually focused on immediate response |
| Industry security reports | Threat intelligence and practical security controls | Explain operational risks and detection approaches | Methods and findings may vary by provider |
| Standards and technical guidance | Secure development and software integrity | Support recommendations for supply-chain protection | Guidance does not guarantee prevention |

**Discussion:** The different source categories complement one another. Incident-specific investigations provide direct evidence about the XZ Utils compromise, while academic studies help explain the broader weaknesses that make software supply-chain attacks possible. Institutional advisories and technical guidance support the development of practical security recommendations.

# 9. Comparative Analysis of Supply-Chain Attack Categories

Software supply-chain attacks can target different stages of software development and distribution [7], [14], [21], [22], [23]. Understanding these categories helps identify where preventive and detective controls should be implemented.

**Table 2. Comparison of software supply-chain attack categories**

| Attack category | Target | Possible security consequence | Relevant security control |
|---|---|---|---|
| Source-code compromise | Source repositories and code changes | Unauthorised or malicious code enters a project | Independent code review and protected branches |
| Contributor compromise | Developer accounts and maintainer access | Attackers gain legitimate-looking access | Multi-factor authentication and access monitoring |
| Build-system compromise | Build scripts and CI/CD infrastructure | Malicious functionality enters generated artifacts | Isolated builds and build-process verification |
| Package-distribution compromise | Release archives and package repositories | Users receive tampered software | Package signing and provenance verification |
| Dependency compromise | Third-party libraries and updates | Downstream applications inherit malicious components | Dependency monitoring and software composition analysis |

**Discussion:** The XZ Utils incident is particularly relevant to contributor trust, source changes, and release/build integrity. These categories may overlap in a sophisticated attack. Consequently, organisations should not depend on a single security control to protect their software supply chains.

# 10. Comparison of Security Detection and Prevention Techniques

Different security techniques address different stages of the software supply chain [11]–[13], [16], [19], [24]. Their effectiveness depends on the threat being investigated and the quality of implementation.

**Table 3. Comparison of security techniques**

| Technique | Primary purpose | Strength | Limitation |
|---|---|---|---|
| Static analysis | Examine source code without execution | Identifies suspicious code patterns and unsafe operations | May miss concealed or build-time malicious behaviour |
| Dynamic analysis | Observe software during execution | Detects suspicious runtime behaviour | Depends on test coverage and execution conditions |
| Software Composition Analysis | Identify dependencies and known vulnerabilities | Improves dependency visibility and vulnerability management | May not detect previously unknown malicious modifications |
| Reproducible builds | Independently verify build outputs | Helps identify unexplained differences between artifacts | Requires controlled and repeatable build environments |
| Software provenance | Record software origin and production information | Improves traceability and accountability | Provenance information must itself be trustworthy |
| Software Bill of Materials | Document software components and dependencies | Supports inventory and incident response | Does not establish that listed components are trustworthy |
| Independent code review | Examine changes through multiple reviewers | Reduces reliance on a single contributor | Cannot guarantee detection of sophisticated concealed changes |

**Discussion:** No single technique is sufficient to prevent all supply-chain attacks. Static and dynamic analysis support detection [16], [19], while reproducible builds, provenance, and independent reviews improve integrity and accountability [9], [11]–[15], [20]. Combining these techniques provides stronger protection than relying on any one approach.

# 11. Recommended Security Measures

The XZ Utils incident demonstrates the need for multiple layers of security across open-source development, build, and distribution processes.

**Table 4. Recommended security measures for open-source software supply chains**

| Identified risk | Recommended measure | Expected security benefit |
|---|---|---|
| Compromised maintainer accounts | Multi-factor authentication and least-privilege access | Reduces unauthorised access |
| Malicious code contributions | Independent review and protected branches | Improves code-change accountability |
| Manipulated build processes | Isolated and reproducible builds | Strengthens build integrity |
| Tampered software releases | Digital signatures and provenance verification | Improves package authenticity |
| Vulnerable or malicious dependencies | Dependency monitoring and SCA tools | Improves visibility into third-party risks |
| Undetected runtime behaviour | Dynamic analysis and behavioural monitoring | Helps identify suspicious execution |
| Delayed incident response | Vulnerability disclosure and response procedures | Supports timely mitigation |
| Limited security resources | Maintainer training and shared security infrastructure | Improves project-wide security maturity |

**Discussion:** These measures should be implemented as a coordinated security strategy. Their effectiveness depends on project size, available resources, threat exposure, and the criticality of the software. Open-source projects should prioritise practical controls that can be maintained consistently over time.

# Figures

- Figure 1: Literature Selection Process (conceptual; numerical screening counts are not yet available).
- Figure 2: Taxonomy of Software Supply-Chain Attacks.
- Figure 3: Software Supply-Chain Security Lifecycle.

The figure source files are maintained in the `figures/` directory. Render them to SVG or PNG and verify that they are embedded and legible in the final submission document.

# 12. Conclusion

The XZ Utils backdoor incident demonstrated that open-source software supply-chain security extends beyond conventional vulnerability detection. It involves the integrity of contributors, source repositories, build systems, release packages, and distribution infrastructure.

The reviewed research and technical investigations show that trusted software components can become attack vectors when weaknesses in development workflows and release verification are exploited.

A defence-in-depth strategy combining contributor security [8], [20], [25],, independent review, reproducible builds, dependency monitoring, software provenance, and behavioural analysis can improve software supply-chain resilience [8], [11]–[16], [19], [20], [24], [25].

The incident also highlights the importance of sustainable security support for open-source communities [8], [20], [21], [25]. As software ecosystems become increasingly interconnected, protecting the integrity of the complete software lifecycle will remain an important cybersecurity research challenge.

---

# References

**IEEE-style numbered reference list.** Numbering follows the corresponding entries in `references/References.bib`. Bibliographic metadata should be checked against the publisher or primary source before final submission.

[1] A. Freund, “Backdoor in upstream xz/liblzma leading to ssh server compromise,” *oss-security* mailing list, Mar. 29, 2024. [Online]. Available: https://www.openwall.com/lists/oss-security/2024/03/29/4

[2] National Institute of Standards and Technology, “CVE-2024-3094 detail,” *National Vulnerability Database*, 2024. [Online]. Available: https://nvd.nist.gov/vuln/detail/CVE-2024-3094

[3] CERT-EU, “Critical vulnerability in XZ Utils,” Security Advisory 2024-032, Apr. 2, 2024. [Online]. Available: https://cert.europa.eu/publications/security-advisories/2024-032/

[4] Red Hat, “CVE-2024-3094,” *Red Hat Customer Portal*, 2024. [Online]. Available: https://access.redhat.com/security/cve/cve-2024-3094

[5] Open Source Security Foundation, “XZ backdoor CVE-2024-3094,” Mar. 30, 2024. [Online]. Available: https://openssf.org/blog/2024/03/30/xz-backdoor-cve-2024-3094/

[6] C. Tafani-Dereeper and K. Knowles, “The XZ Utils backdoor (CVE-2024-3094): Everything you need to know, and more,” *Datadog Security Labs*, Apr. 3, 2024. [Online]. Available: https://securitylabs.datadoghq.com/articles/xz-backdoor-cve-2024-3094/

[7] P. Ladisa, H. Plate, M. Martinez, and O. Barais, “SoK: Taxonomy of attacks on open-source software supply chains,” in *Proc. IEEE Symp. Security and Privacy*, 2023, pp. 1509–1526, doi: 10.1109/SP46215.2023.10179304.

[8] D. Wermke, J. H. Klemmer, N. Wöhler, J. Schmüser, H. S. Ramulu, Y. Acar, and S. Fahl, “Always contribute back: A qualitative study on security challenges of the open source supply chain,” in *Proc. IEEE Symp. Security and Privacy*, 2023, pp. 1545–1560, doi: 10.1109/SP46215.2023.10179378.

[9] M. Nahum, E. Grolman, I. Maimon, D. Mimran, O. Brodt, A. Elyashar, Y. Elovici, and A. Shabtai, “OSSIntegrity: Collaborative open-source code integrity verification,” *Computers & Security*, vol. 144, Art. no. 103977, 2024, doi: 10.1016/j.cose.2024.103977.

[10] P. Przymus and T. Durieux, “Wolves in the repository: A software engineering analysis of the XZ Utils supply chain attack,” in *Proc. 22nd IEEE/ACM Int. Conf. Mining Software Repositories*, 2025, pp. 91–102, doi: 10.1109/MSR66628.2025.00026.

[11] National Institute of Standards and Technology, *Strategies for the Integration of Software Supply Chain Security in DevSecOps CI/CD Pipelines*, NIST SP 800-204D, 2024, doi: 10.6028/NIST.SP.800-204D.

[12] S. Yu, W. Song, X. Hu, and H. Yin, “On the correctness of metadata-based SBOM generation: A differential analysis approach,” in *Proc. 54th Annu. IEEE/IFIP Int. Conf. Dependable Systems and Networks*, 2024, doi: 10.1109/DSN58291.2024.00018.

[13] G. Benedetti, O. Solarin, C. Miller, G. Tystahl, W. Enck, C. Kästner, A. Kapravelos, A. Merlo, and L. Verderame, “An empirical study on reproducible packaging in open-source ecosystems,” in *Proc. 47th IEEE/ACM Int. Conf. Software Engineering*, 2025, doi: 10.1109/ICSE55347.2025.00136.

[14] B. M. Reichert and R. R. Obelheiro, “Software supply chain security: A systematic literature review,” *International Journal of Computers and Applications*, vol. 46, no. 10, pp. 853–867, 2024, doi: 10.1080/1206212X.2024.2390978.

[15] S. Butler, J. Gamalielsson, B. Lundell, C. Brax, A. Mattsson, T. Gustavsson, J. Feist, B. Kvarnström, and E. Lönroth, “On business adoption and use of reproducible builds for open and closed source software,” *Software Quality Journal*, vol. 31, pp. 687–719, 2023, doi: 10.1007/s11219-022-09607-z.

[16] F. N. Fröh, M. F. Gobbi, and J. Kinder, “Differential static analysis for detecting malicious updates to open source packages,” in *Proc. 2023 Workshop on Software Supply Chain Offensive Research and Ecosystem Defenses*, 2023, pp. 41–49, doi: 10.1145/3605770.3625211.

[17] H. Rebatchi, N. Moha, and T. F. D. Bissyandé, “Dependabot and security pull requests: Large empirical study,” *Empirical Software Engineering*, vol. 29, no. 5, 2024, doi: 10.1007/s10664-024-10523-y.

[18] S. Nocera, S. Vegas, G. Scanniello, and N. Juristo, “Software composition analysis and supply chain security in Apache projects: An empirical study,” in *Proc. 22nd IEEE/ACM Int. Conf. Mining Software Repositories*, 2025, pp. 103–115, doi: 10.1109/MSR66628.2025.00027.

[19] S. Muralee, I. Koishybayev, A. Nahapetyan, G. Tystahl, B. Reaves, A. Bianchi, W. Enck, A. Kapravelos, and A. Machiry, “ARGUS: A framework for staged static taint analysis of GitHub workflows and actions,” in *Proc. 32nd USENIX Security Symp.*, 2023. [Online]. Available: https://www.usenix.org/conference/usenixsecurity23/presentation/muralee

[20] S. Amft, S. Höltervennhoff, R. Panskus, K. Marky, and S. Fahl, “Everyone for themselves? A qualitative study about individual security setups of open source software contributors,” in *Proc. IEEE Symp. Security and Privacy*, 2024, pp. 1065–1082, doi: 10.1109/SP54263.2024.00214.

[21] W. Schueller and J. Wachs, “Modeling interconnected social and technical risks in open source software ecosystems,” *Big Data & Society*, 2024, doi: 10.1177/26339137241231912.

[22] B. Ruan, Z. Lin, J. Liu, C. Zhang, K. Ji, and Z. Liang, “Propagation-based vulnerability impact assessment for software supply chains,” in *Proc. IEEE/ACM Int. Conf. Automated Software Engineering*, 2025, pp. 65–77, doi: 10.1109/ASE63991.2025.00014.

[23] Y. Shen, X. Gao, H. Sun, and Y. Guo, “Understanding vulnerabilities in software supply chains,” *Empirical Software Engineering*, vol. 30, Art. no. 20, 2025, doi: 10.1007/s10664-024-10581-2.

[24] M. Lins, R. Mayrhofer, M. Roland, D. Hofer, and M. Schwaighofer, “On the critical path to implant backdoors and the effectiveness of potential mitigation techniques: Early learnings from XZ,” arXiv:2404.08987, 2024. [Online]. Available: https://arxiv.org/abs/2404.08987

[25] R. Sammak, A. L. Rotthaler, H. S. Ramulu, D. Wermke, and Y. Acar, “Developers’ approaches to software supply chain security: An interview study,” in *Proc. 2024 Workshop on Software Supply Chain Offensive Research and Ecosystem Defenses*, 2024, doi: 10.1145/3689944.3696160