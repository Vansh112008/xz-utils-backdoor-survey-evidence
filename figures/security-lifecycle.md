
# Figure 3. Software Supply-Chain Security Lifecycle

```mermaid id="7h3k2p"
flowchart LR
    A["Development"] --> B["Code Review"]
    B --> C["Build and Integration"]
    C --> D["Testing and Verification"]
    D --> E["Release and Signing"]
    E --> F["Distribution"]
    F --> G["Deployment and Monitoring"]

    A -.-> H["Contributor Authentication"]
    B -.-> I["Independent Review"]
    C -.-> J["Secure CI/CD"]
    D -.-> K["Static and Dynamic Analysis"]
    E -.-> L["Provenance and Reproducible Builds"]
    F -.-> M["Package Integrity Verification"]
    G -.-> N["Vulnerability Monitoring"]
```

**Figure 3:** Security checkpoints throughout the software supply-chain lifecycle.

**Relevance:** The XZ Utils incident demonstrates why security controls must extend beyond source-code review to include build systems, release verification, distribution, and monitoring.
```
