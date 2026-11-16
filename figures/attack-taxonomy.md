
# Figure 2. Taxonomy of Software Supply-Chain Attacks

```mermaid
flowchart TD
    A["Software Supply-Chain Attacks"]
    A --> B["Source Code Attacks"]
    A --> C["Contributor and Account Attacks"]
    A --> D["Build-System Attacks"]
    A --> E["Package Distribution Attacks"]
    A --> F["Dependency Attacks"]

    B --> B1["Malicious code injection"]
    B --> B2["Unauthorised code changes"]

    C --> C1["Account compromise"]
    C --> C2["Malicious insider or contributor"]

    D --> D1["Build-script manipulation"]
    D --> D2["Compromised CI/CD pipeline"]

    E --> E1["Tampered release packages"]
    E --> E2["Repository compromise"]

    F --> F1["Dependency confusion"]
    F --> F2["Malicious dependency updates"]
```

**Figure 2:** Classification of major software supply-chain attack categories and representative attack techniques.

**Relevance:** The XZ Utils incident illustrates how contributor trust and release/build processes can be abused to introduce malicious functionality into a software distribution.
```
