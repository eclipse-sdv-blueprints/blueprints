# Associated Blueprints

An **Associated Blueprint** is a solution that uses Eclipse SDV technologies but requires proprietary or otherwise not generally available components to run and demonstrate its use case. It is hosted and maintained outside the Eclipse SDV Blueprints project and is featured on the [Eclipse SDV Blueprints website](https://sdv-blueprints.eclipse.dev/) with a short description and a link.

This page describes why the category exists, what qualifies, what an Associated Blueprint does and does not get, and how a proposal becomes one. The process for standard blueprints is described in the [README](./README.md) and the [onboarding guide](./ONBOARDING.md).

---

## Why this category exists

Standard blueprints operate under Eclipse Foundation governance. They must run and demonstrate their use case using only open-source licensed, generally available components, so that anyone in the community can reproduce them out of the box, in compliance with Eclipse Foundation licensing and IP guidelines. A standard blueprint may additionally support proprietary components, provided it still works without them.

On this page, *proprietary* means not licensed under an [OSI-approved](https://opensource.org/licenses) open-source license. An open-source licensed component can be part of a commercial offering and still be used in a standard blueprint. What matters is whether anyone can reproduce the whole setup on their own, without accepting license terms or usage rights beyond those of an open-source license.

Some valuable real-world integrations cannot meet that bar because they depend on a proprietary platform, a proprietary backend, or a component that is not generally available. They do not fit the standard governance model, but they show how Eclipse SDV technologies are used alongside proprietary offerings, and the community wants them to be visible.

The Associated Blueprint category was introduced for these cases, following the discussion of proposal [#18](https://github.com/eclipse-sdv-blueprints/blueprints/issues/18) with the Eclipse SDV community and program leadership.

## Standard and Associated Blueprints compared

| | Standard Blueprint | Associated Blueprint |
|---|---|---|
| Components | Runs on open-source licensed, generally available components; proprietary components may be supported as an option | Requires proprietary or non-generally available components to run |
| Reproducibility | Anyone can reproduce the use case out of the box on their own infrastructure or hardware, even if the particular hardware is hard to obtain | Requires a proprietary license, an account or restricted access |
| Hosting | Repository under [`eclipse-sdv-blueprints`](https://github.com/eclipse-sdv-blueprints) | Hosted by its owners, outside the Eclipse SDV Blueprints project |
| Governance | Eclipse Foundation Development Process, as part of the Eclipse SDV Blueprints project | Not governed by the Eclipse SDV Blueprints project; the owners decide |
| IP review and licensing | EMO IP review; Eclipse licensing requirements apply | No IP review; the blueprint's own repository must be open-source licensed |
| Committers | Contributors become Eclipse SDV Blueprints committers by election | Maintainers do not become Eclipse SDV Blueprints committers through the Associated Blueprint |
| Website | Full documentation pulled from the repository | Short description and a direct link to the external repository |
| Designation | "Eclipse SDV Blueprint" | "Associated Blueprint" |

## What qualifies

An Associated Blueprint should:

* Demonstrate the use of at least one, preferably more, Eclipse SDV projects in a meaningful way.
* Have running code in a publicly accessible repository. **We are code first** applies here too.
* Publish the content of that repository, meaning the documentation and at least the glue code of the blueprint, under an OSI-approved open-source license.
* Have a named owner or team willing and able to maintain it.
* State clearly in its README which components are proprietary or not generally available, and what a user needs (licenses, accounts, hardware) to reproduce it.

A proposal that can run and demonstrate its use case without proprietary or non-generally available components should follow the standard blueprint process instead, even if it optionally supports them.

## What an Associated Blueprint gets

* **External hosting and autonomy.** The blueprint stays where its team hosts it and is maintained by that team. The Eclipse SDV Blueprints project does not apply its processes or IP reviews to it. The only licensing requirement is the open-source license for the blueprint's own repository, described above.
* **Ecosystem visibility.** The blueprint is featured on the Eclipse SDV Blueprints website with a short description and a direct link to its repository.
* **Official designation.** The team may use "Associated Blueprint" as an official label for the implementation.

## What it does not get

* It is not part of the Eclipse SDV Blueprints project, and no repository is created for it under `eclipse-sdv-blueprints`.
* It is not reviewed, maintained or endorsed by the Eclipse SDV Blueprints committers. The project lists it; it does not vouch for its content, the licensing of the components it requires, or its reproducibility.
* It should not be presented as an "Eclipse SDV Blueprint" or as a project of the Eclipse SDV Blueprints project. The label to use is "Associated Blueprint".

If an Associated Blueprint is hosted in a repository that belongs to another Eclipse Foundation project, that project's governance and Eclipse Foundation rules continue to apply to that repository as usual. The Associated Blueprint status does not change them.

---

## Process

### 1. Proposal

Proposals start the same way as any other blueprint: [create an issue](https://github.com/eclipse-sdv-blueprints/blueprints/issues) in this repository. Proposers who already know their solution requires proprietary or non-generally available components to run can ask for Associated Blueprint status directly in the issue.

A proposal submitted as a standard blueprint may also be redirected to this category during review, if the discussion shows that it cannot meet the open-source and reproducibility requirements.

### 2. Review and vote

The proposal is discussed on the issue. Existing committers then vote on granting Associated Blueprint status, using the same voting rules as for standard blueprints (see the [README](./README.md#step-4-voting)): three +1 and no objections. The Project Lead posts the result on the issue.

Template for the result comment:

```markdown
Voting has concluded. Thank you for submitting this proposal and for your
patience while we discussed it with the Eclipse SDV community.

Standard blueprints operating under Eclipse Foundation governance must run
and demonstrate their use case using only open-source licensed, generally
available components, so that anyone in the community can reproduce them
out of the box. Because this integration requires proprietary or
non-generally available components to run (<components>), it does not fit
the standard governance model, but it represents a real-world use case we
want to support.

The committers have voted to offer this proposal the **Associated
Blueprint** status, as described in
[ASSOCIATED_BLUEPRINTS.md](https://github.com/eclipse-sdv-blueprints/blueprints/blob/main/ASSOCIATED_BLUEPRINTS.md).

If you would like to proceed, please confirm in a reply here and share a
short summary and the repository link you would like us to use on the
website.
```

### 3. Confirmation by the proposers

The proposers confirm on the issue that they want to proceed as an Associated Blueprint and provide:

* the name of the blueprint,
* a short description (two or three sentences) for the website,
* the link to the repository,
* a contact person.

### 4. Listing on the website

The Project Lead, or a committer, opens a pull request to [`blueprints-website`](https://github.com/eclipse-sdv-blueprints/blueprints-website) that adds the blueprint with its short description and repository link, marked as an Associated Blueprint. No documentation is pulled from the external repository.

Once the listing is live, the proposal issue is closed as **completed** with a link to the website entry.

### 5. Keeping the listing current

The owners of an Associated Blueprint are asked to tell the project when the repository moves, the description needs to change, or the blueprint is no longer maintained. Updates are made by pull request to `blueprints-website` or by opening an issue in this repository.

A listing may be removed if its link is broken, the blueprint is no longer maintained, or it no longer uses Eclipse SDV technologies.

## Moving to a standard blueprint

If an Associated Blueprint no longer requires proprietary or non-generally available components to run, its owners can propose it as a standard blueprint. It then follows the full process in the [README](./README.md), including voting, IP review and onboarding.

## Who to ask

Questions about the category or about a specific listing go to the Project Lead, through an issue in this repository or the Eclipse SDV Blueprints Slack channel.
