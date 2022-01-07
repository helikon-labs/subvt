# SubVT Milestone #1 Report

First milestone of SubVT consisted of the following items and output:

| Item                                                   | Output                                                                                          |                                                                                                          |
|--------------------------------------------------------|-------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------|
| Requirements gathering and documentation.              | User stories, feature details and implementation details as issues in the top-level repository. | [link](https://github.com/helikon-labs/subvt/issues?q=is%3Aopen+is%3Aissue+label%3Afeature)              |
|                                                        | Data definition document for the design team.                                                   | [link](https://docs.google.com/document/d/1gVGHBSqji-XJc6luvLDm3ilq08LMVb2hhC3EqZ5jr5Q/edit?usp=sharing) |
| System architecture design and feasibility evaluation. | Architecture design and feasibility evaluation report.                                          | [link](../software/01-subvt_system_architecture.md)                                                      |
| UI/UX designer search, calls and proposal evaluation.  | Reported below.                                                                                 |                                                                                                          |

## UX/UI Design Team Search and Evaluation

We interviewed 8 UX/UI design agencies (1 from our circles and 7 from [Dribbble](https://dribbble.com)) and 2 freelancers (1 from [Toptal](https://toptal.com) and the other from [Dribbble](https://dribbble.com)) after we prepared feature documentation as [issues](https://github.com/helikon-labs/subvt/issues?q=is%3Aopen+is%3Aissue+label%3Afeature) in the top-level project [repository](https://github.com/helikon-labs/subvt).

After the evaluation of each portfolio and proposal and initial calls, we decided to work with [Klad](https://www.klad.design/) due to:
- The aesthetic and functional quality of their past work.
- Interest and experience in the blockchain/cryptocurrency space.
- Professional approach to project management and clearly defined processes.
- Diversity of talent (separate staff for UX design, UI design and 3D modeling) on their team.
- Reasonable time and budget proposal.

We prepared a platform and data definition [document](https://docs.google.com/document/d/1gVGHBSqji-XJc6luvLDm3ilq08LMVb2hhC3EqZ5jr5Q/edit?usp=sharing) for Klad to help them with their undestanding of SubVT and its information architecture.

## Backend Choices

We started with some research on what's available for Substrate in the Rust, Go, Java and Python spaces, and we decided to code the backend in Rust. Not to mention its inherent strengths, Rust makes it much easier to use the existing Substrate/Polkadot codebases, enables us to respond very quickly to runtime and metadata changes, and it is a good investment for our future Substrate projects.

We designed the backend system [architecture](../software/01-subvt_system_architecture.md) after a brief build-one-to-throw-away exploratory coding. Rest of the development effort in the first, [second](./02-milestone_02_report.md) and [third](./03-milestone_03_report.md) milestones was very heavy backend coding, and responding to Polkadot and Kusama runtime and metadata (especially v14) changes.

## Evaluation of Substrate Client Libraries

For the backend, we developed our [custom Substrate client](https://github.com/helikon-labs/subvt-backend/tree/main/subvt-substrate-client) tailored specifically for SubVT's specific needs. There isn't going to be any signed operations or direct node communication from the SubVT iOS/Android apps in this first version. So we currently don't need an iOS/Android Substrate client library. Here is a list of open source repositories that we benefited from while developing the SubVT Substrate client:

- [frame-metadata](https://github.com/paritytech/frame-metadata)
- [SubXT](https://github.com/paritytech/subxt)
- [PolkaJ](https://github.com/emeraldpay/polkaj)
- [Fearless Utils Android](https://github.com/soramitsu/fearless-utils-Android)
