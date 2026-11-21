# 1Hive LLC roadmap

1Hive LLC is an independent contributor to 1Hive. We're working toward a simple experience: point the agent you already use at [1hive.org](https://1hive.org), find useful work, and review what it proposes to do for you.

[Vision and roadmap](https://1hive.io/blog/honey-v1-maintenance-and-roadmap/) · [Start with your agent](https://1hive.org/Participate-with-your-agent) · [Contribution guide](CONTRIBUTING.md)

## Work you can inspect today

- [Honey v1 court-switch discussion](https://github.com/1Hive/1hive.org/issues/3). Local tests are described there. The proposed move from Celeste to Kleros is under discussion, not an adopted or executed change.
- [Juror preview](https://1hive.io/previews/honey/) and its [standalone source](https://github.com/1hive-llc/honey-demo-preview). Try fictional evidence, a sample ballot, and an appeal without a wallet. This is a walkthrough, not a production rehearsal.
- [1hive.org upstream](https://github.com/1Hive/1hive.org) and [the LLC fork](https://github.com/1hive-llc/1hive.org). The upstream is the place for community website contributions. The fork does not serve the live site.

## Proposed work and how to verify it

| Track | Next deliverable | How a reviewer can check it |
| --- | --- | --- |
| Honey v1 court | Draft the court switch for community review. Preserve Conviction proposals and Decision votes. | Review the exact proposed setting change, deployed permissions, and initial juror availability. Reproduce both proposal flows against a named rehearsal state. Follow the [court discussion](https://github.com/1Hive/1hive.org/issues/3). |
| Agent entry point | Help a first-time agent find current work and prepare a useful contribution for human review. | Start a fresh agent at [1hive.org](https://1hive.org). It finds a live task, cites sources, and drafts something reviewable without a wallet or private repo. |
| Governance tools | Document the supported CLI and browser paths for proposers and jurors, including what can be previewed and what requires approval. | Follow the runbook from a clean checkout and reproduce the supported examples. The [Honey CLI source preview](https://github.com/1hive-llc/honey-cli) includes an offline jury and appeal example. |
| Maintenance handoff | Publish a runbook and maintain the public repository map. | A new maintainer can find the canonical source for each project, tell active work from archives, and see where to review or report changes. |

A [Gardens Common Pool](https://app.gardens.fund/gardens/100/0xe2396fe2169ca026962971d3b2e373ba925b6257/0x96dee4849a6ab9e51ae36712794318001515dc91) funding request for maintenance and tooling is separate from the decision to switch courts. This is the pool link, not a submitted funding proposal. Neither decision authorizes the other.

## Repository map

[Historical repository index](ARCHIVE.md) lists the archived forks by area.

- [Public organization repositories](https://github.com/orgs/1hive-llc/repositories): public work and historical archives. Archived forks are references, not supported deployments.
- **Gardens v1:** [protocol](https://github.com/1hive-llc/gardens) and [UI](https://github.com/1hive-llc/gardens-ui).
- **Celeste:** [contracts](https://github.com/1hive-llc/celeste-contracts) and [dashboard](https://github.com/1hive-llc/celeste-dashboard).
- **Public source previews:** [Honey CLI](https://github.com/1hive-llc/honey-cli) and [Honey protocol](https://github.com/1hive-llc/honey-protocol). The protocol source and tests are for review; no court change has been deployed. The [standalone preview](https://github.com/1hive-llc/honey-demo-preview) remains runnable without an install.
