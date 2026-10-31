# Awesome-Collaborative-Code-Review-Software

# Awesome-Collaborative-Code-Review-Software

**Top Collaborative Code Review Software (Opensource) 🌟 Star if you like it! 🌟**



**Curated List of SaaS Products & Open-Source GitHub Projects**

*Focused on Pull Request Workflows, Pre-Commit Review, Inline Comments & Self-Hosted Review Platforms*

**Last updated: November 2026**



This repository tracks notable **SaaS platforms** and **open-source projects** for **Collaborative Code Review Software**. These tools enable teams to review code changes before merge, discuss diffs inline, enforce approval workflows, and integrate review into their version control system—from fully managed platforms with AI-assisted review to self-hosted review engines that give organizations complete control over their code review process.



**Examples** include GitHub Pull Requests, GitLab Merge Requests, Crucible, Gerrit, Review Board, Phabricator, Collaborator, RhodeCode, Reviewable, and Upsource (the category leaders in commercial and open-source space).



**Open-source emphasis**: This section is expanded with every relevant project for self-hosted code review, pre-commit workflows, and open review infrastructure. **Critical note**: The open-source code review landscape is mature but fragmented—**Gerrit** remains the gold standard for Git-based pre-commit review with two-way voting and CI integration , **Review Board** is the most flexible multi-SCM option but has performance limitations , and **RhodeCode** uniquely supports Git, Mercurial, and SVN in one platform with enterprise-grade permissions . **Phabricator is no longer maintained as of June 2021**—do not start new projects on it . No open-source project matches GitHub/GitLab's native PR experience, but for self-hosted control, Gerrit and RhodeCode are production-proven.



Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.



## Table of Contents

- [SaaS/Hosted Platforms](#saas-hosted-platforms)

- [Open-Source GitHub Projects](#open-source-github-projects)

- [How to Contribute](#how-to-contribute)

- [Disclaimer](#disclaimer)



## SaaS/Hosted Platforms



- **[GitHub Pull Requests](https://github.com/features/code-review)**

  **Native code review integrated with GitHub** with inline comments, suggested changes, review assignments, and required approvals. **Pricing**: Free for public repos; included with GitHub paid plans for private. **Free tier**: Yes, with GitHub account. **Best for**: teams already hosting code on GitHub wanting the most seamless review experience—**trade-off**: vendor lock-in; advanced review features tied to paid tiers.



- **[GitLab Merge Requests](https://about.gitlab.com/)**

  **Integrated code review within GitLab** with approvals, threads, and CI integration. **Pricing**: Free tier; paid tiers scale with features. **Free tier**: Yes, limited. **Best for**: teams wanting a single tool for repo, CI, and review—**trade-off**: complex configuration at scale.



- **[Crucible](https://www.atlassian.com/software/crucible)** (Atlassian)

  **Enterprise code review tool** supporting Git, SVN, and Perforce repositories, with deep Jira integration for linking reviews to issues . **Pricing**: Quote-only; enterprise contracts. **Free tier**: None. **Best for**: Atlassian-centric organizations wanting formal peer review with Jira traceability—**trade-off**: separate product from Bitbucket; enterprise pricing.



- **[Reviewable](https://reviewable.io/)**

  **Code review platform fully integrated with GitHub** (and only GitHub). **Pricing**: Free for personal use; paid per user for teams. **Free tier**: Free personal. **Best for**: GitHub teams wanting a more powerful review interface than GitHub's native PRs—**trade-off**: GitHub-only; not for self-hosted.



- **[Collaborator](https://smartbear.com/product/collaborator/overview/)** (SmartBear)

  **Peer code review tool** for teams needing formal review workflows across SVN, Git, TFS, and Perforce. **Pricing**: Quote-only; starting around $12/month per user according to third-party listings . **Free tier**: None. **Best for**: regulated enterprises needing auditable peer review across heterogeneous version control.



- **[Upsource](https://www.jetbrains.com/upsource/)** (JetBrains)

  **Code review and repository browsing** integrated with JetBrains IDEs. **Note**: JetBrains discontinued Upsource; existing customers only. **Pricing**: N/A. **Free tier**: N/A. **Best for**: historical reference—**do not adopt for new projects**.



## Open-Source GitHub Projects



- **[Gerrit](https://github.com/GerritCodeReview/gerrit)**

  **Web-based code review tool for Git** (Apache 2.0) — **the gold standard for pre-commit code review**, used by Android, Chromium, and large-scale open-source projects . **Features**: **Review created by pushing to a special branch** (`refs/for/master`) ; **two-way voting**—verified (CI/Jenkins) and code review ; **comprehensive access control** protecting the repository ; **tick-box per-file review tracking** ; **Jenkins integration** for patch verification . **Tech stack**: Java (.war) . **Deploy**: Self-hosted (Java servlet container). **Trade-off**: **Git-only**—no SVN or Mercurial . **UI is functional but dated**—shows one file at a time, not a rich diff view . **Best for**: Git-centric teams wanting rigorous pre-commit review with CI-gated approvals—especially open-source projects with external contributors where access control and verification matter.



- **[Review Board](https://github.com/reviewboard/reviewboard)**

  **Web-based collaborative code review tool** (MIT) — **the most flexible open-source review platform**, supporting any modern SCM . **Features**: **Pre-commit and post-commit reviews** created via Python script (`rbt post`) ; **supports Git, SVN, Mercurial, Perforce, and more**; **nice UI** with diff viewing . **Tech stack**: Python . **Deploy**: Self-hosted (Apache/lighttpd) . **Trade-off**: **No repository access control**—it does not manage the repository, only the review . **UI is slow loading diffs**—Gerrit and Phabricator are much faster . **Best for**: teams with heterogeneous version control (SVN + Git + Mercurial) needing a single review interface—willing to accept slower diff loading and external repository management.



- **[RhodeCode](https://github.com/rhodecode/rhodecode)**

  **Unified source code management and code review platform** (AGPLv3 Community Edition) — **the only open-source platform supporting Git, Mercurial, and SVN with unified code review** . **Features**: **Inline comments** for instant feedback; **smart commits** to trigger approvals and merges; **custom review workflows**; **reviewer rules** assign the right owners; **event hooks and webhooks** on every action; **full REST API**; **granular permissions** at team, individual, or repository level; **immutable audit log** with 7-year retention and SIEM stream; **LDAP, AD, SAML 2.0, CAS, OAuth, 2FA** authentication; **on-premises, private cloud, or air-gapped** deployment . **Community Edition is free with unlimited users** . **Enterprise Edition** adds SLA support, enterprise auth, and high availability at **$75/user/year** . **Tech stack**: Python. **Deploy**: Self-hosted (Linux). **Trade-off**: **UI can feel outdated** per reviewer feedback . **Mercurial/SVN support is unique but niche**—if you only use Git, Gerrit or GitHub/GitLab are more focused. **Best for**: enterprises with mixed version control (especially Mercurial or SVN alongside Git) needing unified review, granular permissions, and audit trails—especially regulated industries and government labs that cannot use SaaS .



- **[Phabricator](https://github.com/phacility/phabricator)**

  **Suite of open-source tools for code review, project management, and repository hosting** (Apache 2.0) — **historically influential but no longer maintained as of June 1, 2021** . **Features**: Pre-commit review via `arc` CLI; post-commit audits triggered by rules; complete ecosystem including bug tracker, repo browser, and wiki; supports Git, SVN, and Mercurial; used by Facebook and Dropbox historically . **Tech stack**: PHP . **Deploy**: Self-hosted. **Trade-off**: **Unmaintained**—no security patches, no bug fixes, no new features since 2021 . **Do not start new projects on Phabricator.** **Best for**: historical reference only—existing installations should evaluate Gerrit or RhodeCode for migration.



### Additional Strong Open-Source Options



- **Mira - Code Review** — Self-hosted AI code review platform (Apache 2.0). Indexed PR analysis, vulnerability scanning, custom rule configuration, Docker deployment, multi-LLM support . **Note**: AI-assisted review, not traditional peer review workflow. **Best for**: teams wanting AI-generated review comments alongside human review.

- **Gito** — Open-source AI code reviewer for GitHub/GitLab (license per repo). Runs locally or in CI/CD; works with any LLM including self-hosted models (Ollama, LM Studio, vLLM) . **Note**: AI review only—not a review workflow platform. **Best for**: teams wanting private AI-assisted review with local models.

- **Reviewdog** — Automated code review tool that posts review comments from any linter output (MIT) . **Note**: Linter integration, not peer review. **Best for**: automating static analysis feedback into PRs.



**Frameworks for building custom systems**: Combine **Gerrit** for Git-based pre-commit review with **Review Board** for SVN/Mercurial repositories, and **RhodeCode** for unified multi-VCS management with audit trails—creating a code review stack matched to each team's version control and compliance requirements. **Phabricator is excluded from composition**—it is unmaintained and insecure for new deployments.



## How to Contribute



1. Fork the repo.

2. Add/edit entries in `README.md` (follow existing format).

3. Include: name, link, 1–2 sentence description, license (for open-source), and whether it's SaaS or open-source.

4. Submit PR with a short explanation.



Star the repo if you find it useful!



## Disclaimer



- This is a **community-curated** list — not exhaustive and not an endorsement.

- Code review platforms handling proprietary source code must comply with data protection regulations (GDPR, CCPA, etc.) and implement appropriate access controls for intellectual property.

- **The "native VCS review" vs. "dedicated review tool" vs. "AI-assisted review" vs. "unmaintained" distinction is critical.** **GitHub Pull Requests and GitLab Merge Requests** are **native VCS review**—review is integrated into the repository host. **Crucible, Reviewable, Collaborator, Gerrit, Review Board, and RhodeCode** are **dedicated review tools**—they provide deeper review workflows than native VCS features . **Mira, Gito, and Reviewdog** are **AI-assisted or automated review**—they generate comments, not peer review workflows. **Phabricator is unmaintained**—do not adopt . **Choose based on whether you need integrated simplicity, dedicated depth, AI assistance, or multi-VCS support.**

- **Gerrit is the choice for rigorous Git review.** Two-way voting (verified + code review), per-file tick tracking, and CI integration make it the standard for projects like Android . **The trade-off**: Git-only, dated UI, and a learning curve for `refs/for/` workflow.

- **Review Board is the choice for multi-SCM environments**—it supports any modern SCM via Python script . **The trade-off**: no repository access control, slow diff loading .

- **RhodeCode is the only open-source option for unified Git + Mercurial + SVN review** with enterprise permissions and audit trails . **The Community Edition is free with unlimited users**—Enterprise adds SLA support at $75/user/year. **For regulated industries needing on-premises review with audit logs, it is the strongest option.**

- **Phabricator is dead.** Effective June 1, 2021, it is no longer actively maintained . **Do not deploy it for new projects**—security vulnerabilities will not be patched. **Existing users should migrate to Gerrit (Git-only) or RhodeCode (multi-VCS).**

- **Crucible and Collaborator are the commercial dedicated review tools** for teams not wanting self-hosted. Crucible integrates with Jira; Collaborator supports multiple VCS with formal workflows . **Pricing opacity is universal**—both require sales contact.

- Self-hosted open-source solutions require proper infrastructure (Java for Gerrit, Python for Review Board/RhodeCode), security hardening for repository access, and ongoing maintenance. **Code review platforms handle proprietary source code**—ensure your deployment meets your organization's security and IP protection requirements before connecting production repositories.



---



**Made for developers, engineering leads, and organizations building transparent code review solutions.**

Let's make Collaborative Code Review more open, data-driven, and review-workflow-friendly.
