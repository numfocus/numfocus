# Numfocus Github permission process

Numfocus defines default permission levels for repositories. The intention is to share as much as we can publicly and restrict access only when required. There are two types of repositories with access restriction. The ones that contains NumFocus board and management sensitive information, the other ones contains data that can’t be made public for other reasons (surveys, tools, etc.).

Access to sensitive repositories must be requested to the board. Access should be reviewed on a quarterly? basis.
Access to non-sensitive private repository is managed by the ???. 

Approval of access requests are tracked on 

## Numfocus organisation

What is the system to be part of the NF organisation? Do we require contributors to be part of the NF organisation?

## Teams

Teams can only contain people part of the Numfocus organisation on Github.

[1] board and executive directory
[2] staff
[3] specific teams for specific usage if required to access private content  (e.g. summit) 

## Repository configuration

Public by default, master branch protection activated (enforce using a PR to contribute)

## Sensitive repositories:

Only one repository seems to quality for sensitive access restriction:
numfocus-board: only access to the board + executive director

## Private repositories

This list needs to be validated:
disc-survey: contains survey data, restrict to staff ?? 
lgl-import
eventbrite-tools
evolution
staff-tools
NF-projects-DISC-survey
trade-shows
summit-planning

## Tooling

Management of Github can be done manually but is error prone (no review of actions possible prior to applying them, no global view on teams and repositories available, no good reporting mechanism). I would suggest using a management tool like Terraform to manage the Github account. This will provide the following benefits:
Possibility of reviewing the suggested changes in the github organization prior to applying them using a Pull Request. The Pull Request also links to the official approval e-mail/document.
Provide an audit log of all the changes (as the terraform configuration files will be under version control)
One single location to review team memberships
Allows users to contribute PR’s to the terraform configuration but applying them is restricted to some admin users.
The Terraform provide should be configured to have its state file stored encrypted on a remote backend like an S3 bucket. 

For reference: https://www.hashicorp.com/blog/managing-github-with-terraform
