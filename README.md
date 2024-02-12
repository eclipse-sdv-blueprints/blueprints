
# Eclipse SDV Blueprints

A collaborative initiative led by Eclipse SDV members to bring the *Software Defined Vehicle* concepts to life. A crucial aspect of each blueprint is to ensure users can easily reproduce it on their own. This requires well-written and highly clear documentation. Users can utilize blueprints as they are, for inspiration or as a foundation to customize and meet their specific needs.

First and foremost, a blueprint must follow the [**Eclipse SDV TAC Principles**](./assets/sdv-tac-principles.md)

## This repository

Eclipse SDV Blueprints project hosts a collection of blueprints. Each blueprint has its own repository.  This particular repository does not contain any code or a particular blueprint.  It is used for governance purposes only. For exmple, if you want to propose a new blueprint, you can [create an issue](https://github.com/eclipse-sdv-blueprints/blueprints/issues)  with this repository to get started.

## Process and principles for new blueprints

New blueprints will be added to the SDV Blueprints project without EMO interfering. It's up to the SDV Blueprints project and/or SDV working group to decide on the incoming criteria.  We will roughly follow the following process for creation of new blueprint.s

### Step 1: The Proposal

Announce and present the idea for your blueprint.  You will do this by [creating an issue here](https://github.com/eclipse-sdv-blueprints/blueprints/issues).  Be as detailed as possible. Use diagrams and explanations.  Github isues support markdown format so make use of it.

###  Step 2: Process for promotion into a new blueprint

We follow Eclipse foundation guidelines, and when you propose a new blue print, you wil be expected to demonstrate that your blueprint meets some bare minimal criteria:
* Running code: Remember, **We are code first**. Your blueprint must be available for review at a public repository (gitlab/github)
* It should demonstrate the use of at least one, preferably more SDV projects.
* It should demonstrate the existence of a committers and a owner willing and able to maintain the blueprint
* It should satisfy the pre-req documentation and metadata requirements
* It should be compatible with SDV/Eclipse licensing requirements
* We nominate and invite new committers if they are backed by strong code contributions and commitment to their blueprint. New committers will be nominated and voted in based on merit and their contributions  (must involve code), and not just by recommendation.
### Step 3: Comments and review

We will comment and review the proposal using the github issue and help you prepare with the creation of the blueprint.

### Step 4: Voting

Existing committers of the SDV blueprints project vote on the blueprint proposal. The voting will be done by commenting on the proposal with the following:

  * +1 Yes
  *  0 Abstain
  * -1 No

Provisional voting rules: 
   * Three +1 and no objections (-1 must provide a detailed justification) will be needed to onboard the blueprint.
   * Existing SDV blueprints committers, SDV steering commitee members and SDV project leaders, and Eclipse Foundation officers have a vote.
   * Following the voting process, we will create a request with the Eclipse EMO helpdesk to add the new repository and committers for the Blueprints.

### Step 5: Onboarding

We will as the eclipse help desk to:
 * Create a new repository for you blueprint under this organization
 * We will add the committers of the blueprint to the project
 * You will have a month to commit your blueprint and get active.
 * An existing SDV Blueprints committer will sponsor/mentor to each Blueprint propasal once it is accepted to help with bootstrapping the new proposal and with other procedural tasks such as approving pull requests and nominating committers.
 * There must be code associated for each new blueprint proposal.  This code should not be trivial or just document a tutorial.  The code can be contributed as a repository (which will be moved to SDV blueprints) or a pull request.
 * EMO will initiate an IP review for these contributions.
 * The initial code contribution will be one of the factors for establishing merits for new committers for a blueprint proposal, so it is important that contributions which will be used for proof of work are clearly identified and contributors are named.
   * To quote the EMO:

> ... elections of both committers and project leads must include a demonstration of merit. Specifically, the nomination statement for an election should provide examples of how the candidate has demonstrated an understanding of the role they're being elected to. This demonstration is for both the project team and for the community.
>    Describing what the candidate does or will do within the context of the project is not enough. You'll expected to provide links that prove it.  
>    Here are some useful links regarding Committer elections: 
>    - https://www.eclipse.org/projects/handbook/#elections-committer
>    - https://www.eclipse.org/projects/handbook/#contributing-contributors
>    - https://blog.waynebeaton.ca/posts/opensource/hired-a-committer/

## SDV Project Maturity

As a part of the overall quality assurance process, participating in a blueprint will earn SDV projects a *maturity* badge.  These badges will be assigned automatically by blueprints meta-data that can be found in a blueprint project.  This metadata is maintained in a file named `.sdv-blueprint.json` and contains content that is similar to:

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
