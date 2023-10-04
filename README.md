# Eclipse SDV Blueprints
A collaborative initiative led by Eclipse SDV members to bring the "software defined vehicle" concepts to life. A crucial aspect of each blueprint is to ensure users can easily reproduce it on their own. This requires well-written and highly clear documentation. Users can utilize blueprints as they are, for inspiration or as a foundation to customize and meet their specific needs.

## This repository
Eclipse SDV Blueprints project hosts a collection of blueprints. Each blueprint has its own repository.  This particular repository does not contain any code or a particular blueprint.  It is used for governance purposes only. For exmple, if you want to propose a new blueprint, you can [create an issue](https://github.com/eclipse-sdv-blueprints/blueprints/issues)  with this repository to get started.

## Process and principles for new blueprints
New blueprints will be added to the SDV Blueprints project without EMO interfering. It's up to the SDV Blueprints project and/or SDV working group to decide on the incoming criteria.  We will roughly follow the following process for creation of new blueprint.s

### Step 1: The Proposal
Announce and present the idea for your blueprint.  You will do this by [creating an issue here](https://github.com/eclipse-sdv-blueprints/blueprints/issues).  Be as detailed as possible. Use diagrams and explanations.  Github isues support markdown format so make use of it.

###  Step 2: Process for promotion into a new blueprint
When you propose a new blue print you wil be expected to demonstrate that your blueprint meets some bare minimal criteria:
* Running code: Available for review at a public repository (gitlab/github)
* It should demonstrate the use of at least one, preferably more SDV projects.
* It should demonstrate the existence of a committers and a owner willing and able to maintain the blueprint
* It should satisfy the pre-req documentation and metadata requirements
* It should be compatible with SDV/Eclipse licensing requirements

### Step 3: Comments and review
We will comment and review the proposal using the github issue and help you prepare with the creation of the blueprint.

### Step 4: Voting

Existing committers of the SDV blueprints project vote on the blueprint proposal.  The voting will b done by commenting on the proposal with the following:

  * +1 Yes
  * 0  Abstain
  * -1 No 

### Step 5: Onboarding
 We will as the eclipse help desk to:
 * Create a new repository for you blueprint under this organization
 * We will add the committers of the blueprint to the project
 * You will have a month to commit your blueprint and get active.

## SDV Project Maturity
As a part of the overall quality assurance process, participating in a blueprint will earn SDV projects a “maturity” badge.  These badges will be assigned automatically by blueprints meta-data that can be found in a blueprint project.  This metadata is maintained in a file named **.sdv-blueprint** and contains content that is similar to:
```json
{
  "name": "fleet-management",
  "version": "0.1.0",
  "description": "Fleet Management",
  "participatingProjects": [
    { "id": "automotive.kuksa" },
    { "id": "automotive.leda" },
    { "id": "automotive.velocitas" },
    ...
  ]
  ...
}

```


## Inactive Blueprints

We will remove and archive blueprints that are not maintained and/or lack committer support.
