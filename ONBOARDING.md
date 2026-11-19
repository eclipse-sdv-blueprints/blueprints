# Onboarding a New Eclipse SDV Blueprint

This guide describes what happens **after a blueprint proposal has been accepted** by vote, up to the point where the blueprint is live and its contributors are maintaining it as Eclipse committers.

It complements the proposal process described in the [blueprints README](https://github.com/eclipse-sdv-blueprints/blueprints) (Steps 1–4: Proposal, Promotion, Review, Voting) and covers Step 5, *Onboarding*, in detail.

This guide applies to standard blueprints. Solutions that require commercial or non-generally available components to run are handled as [Associated Blueprints](./ASSOCIATED_BLUEPRINTS.md), which are hosted externally and do not go through onboarding.

All Eclipse SDV Blueprints are governed by the [Eclipse Foundation Development Process (EDP)](https://www.eclipse.org/projects/dev_process) and must follow the [Eclipse SDV TAC Principles](./assets/sdv-tac-principles.md). Where this guide and the EDP differ, the EDP wins.

---

## At a glance

| # | Phase | Owner | Outcome |
|---|-------|-------|---------|
| 1 | Declare voting results | Project Lead | Result posted on the proposal issue and on Slack |
| 2 | Provision repository | Project Lead | New repo under `eclipse-sdv-blueprints` |
| 3 | Assign a blueprint mentor | Project Lead | A named existing committer guides onboarding |
| 4 | Prepare the initial pull request | Proposal owners | Code + docs PR, compliant with Eclipse rules |
| 5 | Review, fix, iterate | Proposal owners + Mentor | PR approved, IP review cleared |
| 6 | Go live | Mentor + Project Lead | Code merged, blueprint listed on the website |
| 7 | Maintain and earn committer status | Contributors + Committers | Contributors elected as committers; mentor steps back |

Typical elapsed time from vote to repository is one to three weeks. Proposal owners are expected to submit their initial contribution **within one month** of the repository being created.

---

## Roles

**Project Lead** – leads the Eclipse SDV Blueprints project. Closes the vote, announces results, requests repository provisioning, and assigns the mentor.

**Proposal owners / new contributors** – the people who proposed the blueprint and wrote the code. They are not yet committers on the project.

**Blueprint mentor** – an existing SDV Blueprints committer who sponsors the new blueprint. The mentor reviews and merges pull requests on the contributors' behalf, answers procedural questions, and later nominates contributors for committer status.

**Committers** – existing SDV Blueprints committers. They vote on proposals and on new committer elections.

**EMO (Eclipse Management Organization)** – runs IP review of the initial contribution and administers committer elections.

---

## Phase 1 — Declare the voting results (@Project Lead)

A proposal is accepted with **at least three +1 votes and no -1 votes**. A -1 must come with a detailed justification. Eligible voters are existing SDV Blueprints committers, SDV Steering Committee members, SDV project leads and Eclipse Foundation officers. Votes from others are welcome as signals of community support but do not count toward the quorum.

If the vote has stalled, ping eligible committers directly on the issue (e.g. *"@name please vote. At least 3 committer votes are required."*).

### 1.1 Post the result on the proposal issue

Use this template as a comment on the proposal issue:

```markdown
Congratulations! Voting has concluded. The proposal is approved with
**<N> +1 votes and no objections**, as per the
[process](https://github.com/eclipse-sdv-blueprints/blueprints).

Next steps:

- Repository provisioning starts now: `eclipse-sdv-blueprints/<repo-name>`.
  @<proposer>, confirm the name or propose an alternative.
- Mentor assignment follows: an existing committer will guide the code onboarding.
- Once the repository is ready, prepare a pull request with the initial
  contribution. Follow the
  [onboarding guide](https://github.com/eclipse-sdv-blueprints/blueprints/blob/main/ONBOARDING.md).

Thanks to everyone who reviewed and voted!
```

### 1.2 Announce on Slack

Post in the Eclipse SDV Blueprints channel:

```text
:tada: New SDV Blueprint accepted: *<Blueprint Name>*
The proposal passed with <N> +1 votes and no objections.
Thanks to @<proposer(s)> and all reviewers.
Proposal: https://github.com/eclipse-sdv-blueprints/blueprints/issues/<id>
Repository (coming soon): https://github.com/eclipse-sdv-blueprints/<repo-name>
```

### 1.3 Agree on the repository name

Confirm the repository name with the proposers before requesting it. Prefer short, lowercase, hyphenated names that describe the use case, for example `service-to-signal`, `e2e-vehicle-signals`, `carmate`.

---

## Phase 2 — Provision the repository (@Project Lead)

Repositories in the `eclipse-sdv-blueprints` organization are managed as code through [Otterdog](https://github.com/eclipse-csi/otterdog), via the [`eclipse-sdv-blueprints/.eclipsefdn`](https://github.com/eclipse-sdv-blueprints/.eclipsefdn) repository.

1. Open a pull request against `.eclipsefdn` that adds the new repository, referencing the proposal issue (`Add <repo-name> blueprint repository, see eclipse-sdv-blueprints/blueprints#<id>`).
2. Once merged, the `eclipse-otterdog` bot applies the change and the repository appears.
3. If needed, open an [EMO helpdesk](https://gitlab.eclipse.org/eclipsefdn/helpdesk) ticket for anything Otterdog cannot handle.
4. Comment on the proposal issue with the repository URL:

```markdown
Repository provisioned and ready:
https://github.com/eclipse-sdv-blueprints/<repo-name>

Proposal phase complete. @<proposer>, prepare a pull request to bring the
blueprint into Eclipse SDV and submit it within one month. Welcome aboard!
```

5. Close the proposal issue as **completed**.

---

## Phase 3 — Assign a blueprint mentor (@Project Lead)

Every new blueprint gets a mentor who is an existing SDV Blueprints committer. Because proposal owners are not yet committers, **they cannot merge their own pull requests**; the mentor does this for them.

Pick a mentor whose technical background matches the blueprint (e.g. someone familiar with uProtocol, Kuksa or Ankaios if the blueprint uses them). Proposers may suggest a mentor.

Confirm availability with the mentor first, then announce on the issue:

```markdown
Mentor assigned: @<mentor>. Work with them to start the code contribution
and to follow due process for adding new committers.
```

**Mentor responsibilities**

- Review the initial contribution and follow-up PRs, and merge them once approved.
- Help contributors with Eclipse procedures (ECA, IP review, licensing, metadata).
- Make sure the initial contribution and its authors are clearly identified, because it is the evidence of merit for later committer elections.
- Nominate contributors for committer status when they have demonstrated merit (Phase 7).

---

## Phase 4 — Prepare the initial pull request (@Proposal owners)

The initial contribution is submitted as a **pull request to the new repository** (not as a direct push, and not by transferring the old repo). Code from a hackathon or personal repository is welcome as the starting point; acknowledge its origins in the README.

The contribution must be real, running code. It should not be trivial or only document a tutorial (*"We are code first"*).

### 4.1 Eclipse Foundation contribution requirements

Before opening the PR, every person whose commits are included must:

- [ ] Have an [Eclipse Foundation account](https://accounts.eclipse.org/user/register) with their **GitHub username** linked.
- [ ] Have signed the [Eclipse Contributor Agreement (ECA)](https://www.eclipse.org/legal/ECA.php).
- [ ] Author commits with the **same email address** registered with the Eclipse account. The ECA check on the PR fails otherwise.

The repository content must include:

- [ ] A `LICENSE` file. Eclipse SDV Blueprints use the **Apache License 2.0** unless agreed otherwise with the project lead.
- [ ] A license/copyright header in every source file, e.g.:

  ```text
  Copyright (c) <YEAR> Contributors to the Eclipse Foundation

  See the NOTICE file(s) distributed with this work for additional
  information regarding copyright ownership.

  This program and the accompanying materials are made available under the
  terms of the Apache License Version 2.0 which is available at
  https://www.apache.org/licenses/LICENSE-2.0

  SPDX-License-Identifier: Apache-2.0
  ```

- [ ] A `NOTICE.md` listing the project, license, source location and third-party content.
- [ ] A `CONTRIBUTING.md` explaining how to contribute (ECA, PR process).
- [ ] A `SECURITY.md` pointing to the [Eclipse vulnerability reporting process](https://www.eclipse.org/security/).
- [ ] A dependency check of all third-party libraries and container images with the [Eclipse Dash License Tool](https://github.com/eclipse/dash-licenses). Anything flagged as "restricted" must be reviewed (the tool can open IP review requests automatically).
- [ ] No secrets, API keys, credentials or personal data in code, configuration or history.
- [ ] No binaries or large generated artefacts that can be built from source.

The EMO runs an **IP review** of the initial contribution. Merging must wait until it is cleared (the mentor coordinates this).

### 4.2 Blueprint metadata

Add a `.sdv-blueprint.json` file at the repository root. It is used to award the SDV Blueprint badge and maturity credits to participating SDV projects:

```json
{
  "name": "<repo-name>",
  "version": "0.1.0",
  "description": "<one-line description>",
  "participatingProjects": [
    { "id": "automotive.kuksa" },
    { "id": "automotive.ankaios" }
  ]
}
```

Use the official Eclipse project IDs (as shown on [projects.eclipse.org](https://projects.eclipse.org)).

### 4.3 Documentation for the ESBP website

Each blueprint must be easy to reproduce. The repository needs at minimum:

- [ ] `README.md` – what the blueprint shows, which SDV projects it uses, an architecture picture, and a link to the getting-started guide.
- [ ] A **getting-started guide** a newcomer can follow end to end, including prerequisites (hardware, OS, tools) and expected results.
- [ ] Architecture documentation with diagrams.
- [ ] Guidance for variations users are likely to want, such as running without special hardware (simulation or mock mode) or swapping a component (e.g. a different LLM provider).
- [ ] A troubleshooting section.

The [ESBP website](https://sdv-blueprints.eclipse.dev/) is built with Docusaurus 2 from [`blueprints-website`](https://github.com/eclipse-sdv-blueprints/blueprints-website). It **pulls markdown directly from the `main` branch** of each blueprint repository using `docusaurus-plugin-remote-content`. To make that work smoothly:

- [ ] Put website-facing pages in a `docs/` folder (e.g. `docs/introduction.md`, `docs/architecture.md`, `docs/getting-started.md`, `docs/components.md`).
- [ ] Keep each page self-contained, and use stable file names; renames break the website.
- [ ] Keep images in `docs/img/` and reference them as `./img/<file>`. The website rewrites these to raw GitHub URLs.
- [ ] Write MDX-compatible markdown: self-close HTML tags (`<br />`, `<img ... />`), avoid inline `style="..."` attributes, and leave a blank line before closing `</details>`.
- [ ] In Mermaid diagrams, use plain ASCII characters (e.g. no middle dot `·`).
- [ ] Avoid relative links to files that will not be published on the website; link to the GitHub URL instead.

### 4.4 Open the pull request

- Target the `main` branch of the new repository.
- Title it clearly, e.g. `Initial contribution of the <Blueprint Name> blueprint`.
- In the description, list **all contributors and their GitHub handles**, link the proposal issue, and summarise what is included. This record supports later committer elections.
- Mention the mentor (`@<mentor>`) for review.

---

## Phase 5 — Review, fix and iterate (@Proposal owners, @Mentor)

- The mentor and other committers review for code quality, reproducibility, documentation and Eclipse compliance.
- At least one reviewer should **try the getting-started guide** on a clean setup and report findings on the PR.
- Proposal owners address feedback by pushing new commits to the same PR. Keep discussion on the PR so the history is visible.
- Typical feedback from previous blueprints has included: adding a getting-started guide to the README, updating the architecture picture, adding a short guide for switching components, and providing a mock or simulation mode for users without the full hardware.
- The ECA check and any CI checks must be green, and the IP review must be cleared, before the mentor merges.

---

## Phase 6 — The blueprint goes live (@Mentor, @Project Lead)

Once the PR is approved and merged, the blueprint is live. To publish it on the website, open a PR to [`blueprints-website`](https://github.com/eclipse-sdv-blueprints/blueprints-website) that adds:

1. **`docusaurus.config.js`** – a `docusaurus-plugin-remote-content` entry pointing at `https://raw.githubusercontent.com/eclipse-sdv-blueprints/<repo-name>/main/docs`, listing the documents, with a `modifyContent` function if image paths or MDX fixes are needed.
2. **`sidebars.js`** – a new category under *Blueprints Documentation* linking the pages.
3. **`src/components/HomepageFeatures/index.tsx`** – a homepage card with title, short description and repository link.
4. **Footer** (`docusaurus.config.js`) – a link under *Docs*.

Verify locally with `yarn install && yarn build` (warnings about broken links are worth fixing), then merge.

Finally:

- [ ] Announce on Slack that the blueprint is live, with links to the repository and website page.
- [ ] Optionally present the blueprint at a Blueprints community call or SDV Community Day.

---

## Phase 7 — Maintain the blueprint and earn committer status (@Contributors, @Committers)

New contributors keep improving the blueprint through pull requests, reviewed and merged by the mentor. Sustained, quality contributions are the path to becoming a committer.

### 7.1 Committer nomination

When a contributor has demonstrated merit, an **existing committer (usually the mentor) nominates them** through the project's page on [projects.eclipse.org](https://projects.eclipse.org) using the committer election process in the [Eclipse Project Handbook](https://www.eclipse.org/projects/handbook/#elections-committer).

The nomination statement must **demonstrate merit with links**. Describing what the candidate does or will do is not enough. Include links to:

- the initial contribution PR and the commits authored by the candidate,
- follow-up PRs (features, fixes, documentation),
- reviews, issue triage and community support.

Committers vote within the election period defined by the EDP. Once the election passes and the candidate completes the Eclipse committer paperwork, they gain write access.

Useful references:

- [Committer elections](https://www.eclipse.org/projects/handbook/#elections-committer)
- [Contributors and committers](https://www.eclipse.org/projects/handbook/#contributing-contributors)
- [On "hiring" a committer](https://blog.waynebeaton.ca/posts/opensource/hired-a-committer/)

### 7.2 After committer status

Committers can review and merge pull requests directly and maintain the blueprint **without the mentor**. They also take on project responsibilities: voting on new proposals and elections, keeping documentation current, and responding to issues.

### 7.3 Staying active

Blueprints that are no longer maintained or lack committer support **are archived**. Keep the blueprint working with current versions of the SDV projects it uses, and keep the website documentation accurate.

---

## Reference examples

| Blueprint | Proposal | Repository |
|-----------|----------|------------|
| Service-to-Signal | [#15](https://github.com/eclipse-sdv-blueprints/blueprints/issues/15) | [service-to-signal](https://github.com/eclipse-sdv-blueprints/service-to-signal) |
| E2E Vehicle Signals and Fleet Analytics | [#22](https://github.com/eclipse-sdv-blueprints/blueprints/issues/22) | [e2e-vehicle-signals](https://github.com/eclipse-sdv-blueprints/e2e-vehicle-signals) |
| CarMate (AI-powered in-vehicle companion) | [#23](https://github.com/eclipse-sdv-blueprints/blueprints/issues/23) | [carmate](https://github.com/eclipse-sdv-blueprints/carmate) |

## Who to ask

| Question | Ask |
|----------|-----|
| Process, voting, repository, mentor assignment | Project Lead |
| Code review, merging, Eclipse procedures | Your blueprint mentor |
| IP review, ECA, licensing, elections | EMO via the [helpdesk](https://gitlab.eclipse.org/eclipsefdn/helpdesk) |
| Website integration | `blueprints-website` issues |
| Anything else | The Eclipse SDV Blueprints Slack channel |
