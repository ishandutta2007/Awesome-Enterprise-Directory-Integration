# Awesome-Enterprise-Directory-Integration

# Awesome-Enterprise-Directory-Integration

**Top Enterprise Directory Integration (Opensource) 🌟 Star if you like it! 🌟**



**Curated List of SaaS Products & Open-Source GitHub Projects**

*Focused on LDAP Directories, Identity Federation, AD Bridging & Self-Hosted Directory Services*

**Last updated: November 2026**



This repository tracks notable **SaaS platforms** and **open-source projects** for **Enterprise Directory Integration**. These tools enable organizations to centralize user identities, authenticate against on-premises or cloud directories, and federate access across applications—from fully managed identity platforms with AD sync to open-source LDAP servers and integrated identity suites that give teams complete control over their directory infrastructure.



**Examples** include Microsoft Entra ID, Okta Universal Directory, PingDirectory, JumpCloud, OneLogin, Google Cloud Directory Sync, CyberArk Identity, AWS Directory Service, ForgeRock (Ping), and Atlassian Directory (the category leaders in commercial space).



**Open-source emphasis**: This section is expanded with every relevant project for self-hosted directory services, LDAP integration, and open identity management. **Critical note**: The open-source landscape is anchored by **OpenLDAP**—the reference implementation and most widely deployed directory outside Active Directory —and **389 Directory Server**—Red Hat's enterprise-grade LDAP server built for tens of millions of entries . **FreeIPA** bundles 389 DS with Kerberos and PKI for a complete Linux identity suite , while **Kanidm** rethinks the directory with modern protocols and safe defaults . No open-source project matches Entra ID's cloud sync or Okta's integration catalog, but for core directory services, the options are production-proven.



Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.



## Table of Contents

- [Sector Overview & Market Dynamics](#sector-overview--market-dynamics)
- [SaaS/Hosted Platforms](#saas-hosted-platforms)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## Sector Overview & Market Dynamics

The global Identity and Access Management (IAM) and directory integration market is valued between $25–$30 billion and projected to surpass $60–$75 billion by the 2030s (10–15% CAGR). The market exhibits a moderately concentrated core dominated by major hyperscalers and platform giants (notably Microsoft Entra ID alongside AWS, Google, and Okta), surrounded by a fragmented perimeter of specialized vendors addressing privileged access, cross-platform endpoint management, and hybrid enterprise directory federation.

## SaaS/Hosted Platforms

| Platform | Starting Price | Free Tier / Trial Limits | Company Size (Valuation / Revenue) | Best For & Key Trade-Offs |
|---|---|---|---|---|
| **Microsoft Entra ID** | Free (bundled core); Premium P1 at $6.00/user/month; P2 at $9.00/user/month | Free tier includes up to 50,000 directory objects (auto-increases to 300,000 objects with a verified custom domain) | ~$3.1T Market Cap (~$245B Ann. Revenue) | Native Windows/M365 AD sync, enterprise Conditional Access; narrower 3rd-party integration catalog than Okta (~3,000 vs 7,000 apps). |
| **AWS Directory Service** | $0.05/hour (~$36/month for Simple AD / AD Connector Small); $0.24/hour total for Managed Microsoft AD Standard (2 domain controllers) | 30-day free trial with 1,500 domain controller hours total across managed directories (covers 2 DCs continuously for 30 days) | ~$2.2T Market Cap (~$105B+ AWS Ann. Revenue Run Rate) | AWS workloads requiring managed AD or LDAP connector; lock-in to AWS infrastructure ecosystem. |
| **Google Cloud Directory Sync (GCDS)** | Free utility (paired with Google Workspace starting at $6.00/user/month or Cloud Identity Free) | 100% free tool forever; Cloud Identity Free includes 50 user licenses (Workspace offers a 14-day free trial up to 10 users) | ~$2.1T Market Cap (~$40B+ GCP Ann. Revenue Run Rate) | Google Workspace environments syncing from on-prem Active Directory/LDAP; connector utility only, not an independent directory. |
| **Atlassian Directory (Atlassian Guard)** | Included in standard cloud; Atlassian Guard Standard starts at $4.00/user/month; Guard Premium at $8.00/user/month | 30-day free trial of Atlassian Guard (unlimited user evaluation during trial period); basic user management free with cloud products | ~$63B Market Cap (~$4.4B Ann. Revenue) | Atlassian Cloud customers needing centralized SAML SSO, SCIM provisioning; scoped exclusively to Atlassian product suite. |
| **CyberArk Identity** | ~$2.00 to $5.00/user/month (Workforce Identity SSO/Adaptive MFA baseline, billed annually) | 14-day free trial with full evaluation access in a guided trial tenant sandbox | ~$15B Market Cap (~$1.0B Ann. Revenue) | Enterprises prioritizing high-assurance Privileged Access Management (PAM) alongside directory federation; complex deployment footprint. |
| **Okta Universal Directory** | $6.00/user/month (Workforce Starter tier including SSO, MFA, and Universal Directory; $1,500/year contract minimum) | 30-day free trial (up to 10 active users, 5 active workflows, full platform feature access) | ~$14B Market Cap (~$2.6B Ann. Revenue) | Heterogeneous cross-vendor SaaS estates requiring deep integration library (7,000+ connectors); premium pricing structure and previous security incidents. |
| **PingDirectory / Ping Identity** | $3.00/user/month (PingOne for Workforce Essential tier; annual enterprise contracts) | 30-day free trial of PingOne platform (sandbox up to 1,000 active evaluation identities) | ~$2.8B Acquisition Valuation by Thoma Bravo (~$350M–$500M+ Ann. Revenue) | Complex enterprise and hybrid environments requiring multi-forest federation, self-hosted directories, and DaVinci orchestration; high operational overhead. |
| **JumpCloud** | $9.00/user/month (Device Management, annual) or $11.00/user/month (SSO, annual) | 30-day full-featured free trial with zero functional restrictions (legacy 10-user free tier grandfathered only before Feb 2024) | ~$2.6B Valuation (Series F) (~$105M–$150M ARR) | Cloud-first SMBs and heterogeneous fleets (macOS/Linux/Windows) needing unified directory and MDM; pricing scales quickly across multi-module add-ons. |
| **OneLogin** | $2.00 to $4.00/user/month (Basic SSO starting at $2.00/user/month; Advanced plan at $4.00/user/month) | 30-day free trial with full feature evaluation (cloud directory sync, desktop/mobile SSO, MFA, no credit card required) | ~$500M Acquisition Estimate by Quest Software (~$50M+ ARR) | Mid-market enterprises wanting streamlined directory sync, smart MFA, and straightforward SSO; fewer cutting-edge governance features. |

## Open-Source GitHub Projects



- **OpenLDAP**

  **Reference open-source LDAP implementation** (OpenLDAP Public License, BSD-style) — **the most widely deployed directory outside Active Directory**, extremely fast and endlessly configurable . **Features**: **Full LDAPv3** with high-performance MDB backend; **flexible replication** including multi-provider; **overlays** for password policy, referential integrity, and access logging; **fine-grained ACLs**; runs at very large entry counts . **Tech stack**: C. **Deploy**: Self-hosted (packages, Docker). **Trade-off**: **Configuration is famously unforgiving** with a steep learning curve; **no modern protocols**—no OIDC, SAML, or web console by default; you build everything above the directory yourself . **Best for**: teams wanting a pure, high-performance LDAP directory they fully control—willing to add identity provider layers (Keycloak, Authentik) for modern protocols.



- **389 Directory Server**

  **Enterprise-grade LDAP server** (GPL-3.0) — **the enterprise-focused LDAP server maintained by Red Hat**, designed for very large deployments handling tens of millions of entries . **Features**: **Multi-supplier replication** with conflict resolution; **administration console** and CLI tooling; **online schema and configuration changes** without restart; **designed for tens of millions of entries**; **Active Directory user/group synchronization** . **Tech stack**: C. **Deploy**: Self-hosted (packages, Docker). **Trade-off**: **Heavier footprint than OpenLDAP**; smaller community outside Red Hat ecosystem; still a directory—modern protocols need an identity provider above it . **Best for**: enterprises needing proven replication at scale with better management tooling than OpenLDAP—especially those already in the Red Hat ecosystem.



- **FreeIPA**

  **Integrated identity management suite** (GPL-3.0) — **the complete Linux identity solution**, bundling 389 Directory Server, MIT Kerberos, Dogtag CA, DNS, and a policy engine into one system with a web UI . **Features**: **Integrated LDAP, Kerberos, CA, DNS, and NTP**; **host-based access control** (HBAC); **centralized sudo rules**; **cross-forest trust with Active Directory**; **certificate issuance** through Dogtag; **web UI and comprehensive CLI** . **Tech stack**: C, Python. **Deploy**: Self-hosted (Linux). **Trade-off**: **Linux/Unix focused**—no Windows endpoint management; replication and upgrades require care; substantial system to operate for a small estate . **Best for**: Linux estates needing Active Directory-equivalent centralized authentication, host access control, and sudo rules—especially those with AD trust requirements .



- **Kanidm**

  **Modern identity platform in Rust** (MPL-2.0) — **a deliberate rethink of the directory**, with safe defaults and low operational burden . **Features**: **Own directory** alongside **OAuth 2.0 and OIDC**; **WebAuthn as first-class authentication**; **Unix account support**; **LDAP offered as compatibility interface** rather than primary protocol; designed for safe defaults . **Tech stack**: Rust. **Deploy**: Self-hosted. **Trade-off**: **Newer and smaller ecosystem** than OpenLDAP or 389 DS; LDAP is secondary—not for legacy LDAP-dependent applications. **Best for**: teams wanting a modern identity platform with correct defaults instead of another LDAP server—especially those building new infrastructure without legacy constraints.



- **Samba Active Directory**

  **Open-source AD domain controller** (GPL-3.0) — **the only credible open-source path to serving Windows clients a real domain** without Microsoft licensing . **Features**: **Active Directory domain controller** functionality for Windows clients; **Kerberos, LDAP, and DNS** as an integrated domain; **Group Policy support**; **file and print services** alongside directory; **replication** with other Samba DCs and Windows DCs . **Tech stack**: C. **Deploy**: Self-hosted (Linux). **Trade-off**: **Feature parity with modern AD is incomplete**, particularly for newer functional levels; **complex to operate correctly**, especially replication and DNS; does not provide the cloud identity layer Entra supplies . **Best for**: organizations needing Windows domain services without Windows Server licensing—willing to accept incomplete parity and operational complexity.



### Additional Strong Open-Source Options



- **Keycloak** — Open-source identity and access management (Apache 2.0). OIDC, SAML, LDAP/AD federation, identity brokering. **Note**: **Identity provider, not a directory**—it federates to directories (OpenLDAP, 389 DS, AD) but does not replace them . **Best for**: adding modern SSO protocols on top of an existing LDAP directory.

- **Apache Directory Server** — Embeddable LDAP server (Apache 2.0). Java-based, embeddable in applications. **Note**: Less commonly deployed than OpenLDAP or 389 DS; smaller community. **Best for**: Java applications needing an embedded directory.

- **Univention Corporate Server (UCS)** — Open-source IT management platform (open source). Integrates OpenLDAP/Samba AD with a management console and App Center . **Note**: Broader platform than pure directory—includes virtualization and app deployment. **Best for**: SMBs wanting an integrated directory and IT management platform.



**Frameworks for building custom systems**: Combine **OpenLDAP** or **389 Directory Server** for the directory core with **Keycloak** for modern SSO protocols and **FreeIPA** for integrated Linux identity management—creating a layered open-source directory stack. **None of these match Entra ID's cloud sync or Okta's integration catalog**, but for core directory services, the options are production-proven.



## How to Contribute



1. Fork the repo.

2. Add/edit entries in `README.md` (follow existing format).

3. Include: name, link, 1–2 sentence description, license (for open-source), and whether it's SaaS or open-source.

4. Submit PR with a short explanation.



Star the repo if you find it useful!



## Disclaimer



- This is a **community-curated** list — not exhaustive and not an endorsement.

- Enterprise directory platforms handling user identities and credentials must comply with data protection regulations (GDPR, CCPA, etc.) and implement appropriate access controls.

- **The "directory server" vs. "identity management suite" vs. "identity provider" distinction is critical.** **OpenLDAP and 389 Directory Server** are **directory servers**—they store and serve LDAP data but lack modern protocols and self-service . **FreeIPA** is an **identity management suite**—it bundles directory, Kerberos, PKI, and policy . **Keycloak** is an **identity provider**—it adds OIDC/SAML federation on top of directories . **Samba AD** is an **AD domain controller**—it serves Windows clients but has incomplete parity . **Choose based on whether you need raw LDAP, integrated Linux identity, modern SSO, or Windows domain services.**

- **OpenLDAP is the most widely deployed open-source directory**—ubiquitous, fast, and flexible . **The trade-off**: configuration is unforgiving, and it has no modern protocols. **Pair it with Keycloak for OIDC/SAML and a web console.**

- **389 Directory Server is the enterprise-grade LDAP choice**—multi-supplier replication, administration console, and design for tens of millions of entries . **The trade-off**: heavier footprint; smaller community outside Red Hat.

- **FreeIPA is the complete Linux identity suite**—Kerberos, PKI, HBAC, and sudo rules out of the box, with AD trust for hybrid environments . **The trade-off**: Linux-focused; substantial system to operate. **For Linux estates needing AD-equivalent centralized policy, it is the strongest open-source option.**

- **Kanidm is the modern alternative**—Rust, WebAuthn-first, OIDC built in, LDAP as compatibility . **The trade-off**: newer and smaller ecosystem; not for legacy LDAP-dependent apps.

- **Samba AD is the only open-source path to Windows domain services**—but parity is incomplete and operations are complex . **Do not evaluate it as a full AD replacement without accepting those limits.**

- Self-hosted open-source solutions require proper infrastructure (servers, replication topology, backup), security hardening, and ongoing maintenance. **Directory services are the keys to your kingdom**—ensure your deployment meets your organization's security and compliance requirements before migrating production identities.



---



**Made for identity architects, system administrators, and organizations building transparent directory integration solutions.**

Let's make Enterprise Directory Integration more open, data-driven, and identity-aware.
