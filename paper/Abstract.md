# Abstract

The XZ Utils backdoor incident (CVE-2024-3094), discovered in March 2024, exposed significant weaknesses in the security of open-source software supply chains. The incident involved malicious modifications introduced into XZ Utils, a widely used data-compression utility, through a sophisticated compromise of its development and release process. The malicious code could interfere with the authentication process of OpenSSH in affected Linux environments, creating a serious potential security risk.

This survey examines the XZ Utils incident in the broader context of open-source software supply-chain security. It reviews technical investigations, vulnerability advisories, and academic research concerning malicious code injection, contributor trust, dependency management, build-system integrity, reproducible builds, and software provenance. The literature is organised thematically to identify common security weaknesses, compare existing detection and prevention approaches, and examine gaps in current research.

The analysis highlights that software supply-chain security cannot depend solely on conventional source-code review. Effective protection requires a defence-in-depth approach incorporating contributor verification, independent code review, secure build pipelines, release integrity checks, dependency monitoring, and timely vulnerability response. The survey concludes by identifying research challenges related to malicious contributor detection, build reproducibility, and the security of community-maintained open-source projects.

**Keywords:** XZ Utils, CVE-2024-3094, software supply-chain security, open-source software, backdoor, software integrity, reproducible builds, dependency security.
