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
- [SaaS/Hosted Platforms](#saas-hosted-platforms)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

- **Microsoft Entra ID**
  **Cloud identity and access management** with hybrid sync to on-premises Active Directory. **Pricing**: Bundled in M365 E3/E5; Premium P1/P2 add-ons **$6–$9/user/month** . **Free tier**: Limited free tier available. **Best for**: Microsoft-centric organizations wanting native AD sync and Conditional Access—**trade-off**: outside Microsoft ecosystem, integration ecosystem narrower than Okta (~3,000 vs. 7,000) .

- **Okta Universal Directory**
  **Vendor-neutral identity platform** with the deepest integration catalog. **Pricing**: Per-user, per-module; **$2–$15/user/month** depending on modules; costs stack across SSO, MFA, lifecycle, and governance . **Free tier**: Developer edition available. **Best for**: heterogeneous SaaS estates wanting identity independent of productivity vendor—**trade-off**: premium pricing; 2022/2023 breaches damaged trust .

- **PingDirectory / Ping Identity (incl. ForgeRock)**
  **Enterprise identity platform** with self-hosted and hybrid deployment options. **Pricing**: PingOne for Workforce per-user/month; larger deployments quoted . **Free tier**: None. **Best for**: regulated enterprises needing self-hosted directories, deep federation, and orchestration via DaVinci—**trade-off**: dedicated identity engineers required; ForgeRock merger created roadmap uncertainty .

- **JumpCloud**
  **Cloud directory platform** for identity, access, and device management. **Pricing**: Tiered per-user pricing; **free tier for up to 10 users**. **Free tier**: Yes. **Best for**: organizations without Active Directory wanting unified directory and device management—especially Mac-heavy environments .

- **OneLogin**
  **Cloud IAM platform** with directory integration and SSO. **Pricing**: Quote-only; tiered by users. **Free tier**: Trial available. **Best for**: mid-market organizations wanting straightforward directory and SSO.

- **Google Cloud Directory Sync (GCDS)**
  **Directory synchronization tool** for Google Workspace. **Pricing**: Free with Google Workspace. **Free tier**: Included with Workspace. **Best for**: Google Workspace organizations syncing from Active Directory or LDAP—**note**: sync tool, not a standalone directory.

- **CyberArk Identity**
  **Identity security platform** with directory integration and privileged access. **Pricing**: Quote-only. **Free tier**: None. **Best for**: enterprises prioritizing privileged access alongside directory services.

- **AWS Directory Service**
  **Managed Microsoft AD or LDAP** in AWS. **Pricing**: Standard and Enterprise editions; per-directory and per-hour pricing. **Free tier**: Limited trial. **Best for**: AWS-centric organizations needing managed AD or LDAP—**trade-off**: AWS ecosystem lock-in.

- **Atlassian Directory**
  **Identity management** within Atlassian Cloud. **Pricing**: Included with Atlassian subscriptions; Atlassian Guard for advanced. **Free tier**: Limited. **Best for**: Atlassian customers needing user provisioning and SSO—**not** a general-purpose directory.

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
