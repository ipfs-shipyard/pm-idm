# IDM - Identity Manager

The Identity Manager - IDM for short - is a unified digital wallet based on open-standards that aims to support multiple decentralized identities.

## Documents

Here is a list of some useful documents. If you're interested in collaborating, please check [Contributing](#contributing).

[💡 Concept](docs/idm-concept.md)   
[📐 IDM Information Architecture](docs/images/diagram_information-architecture.png)   
[🛠 IDM Breakdown](https://docs.google.com/document/d/1g0TjSPjEM4pryPwJTGhIeE4DBsj-VJpz_JqbfllJUgA)  
[🗓 IDM Workplan](https://docs.google.com/spreadsheets/d/1Venqgkcao2Lcje0mkCxr9u0H037aC3H5IxMfsoaeMoE)   
[📖 IDM Specification (WIP)](https://cryptpad.fr/code/#/2/code/view/x6emT-0hXpN4eg-9wZEHaKsmgOEU+jdcyBx9-pG6nQQ)  

## Team

- [André Cruz](https://github.com/satazor) - Software engineer
- [André Sousa](https://github.com/andreforsousa) - Designer
- [Cátia Pereira](https://github.com/catiatpereira) - Project Manager
- [Paulo Marcos](https://github.com/paulobmarcos) - Software engineer
- [Pedro Santos](https://github.com/PedroMiguelSS) - Software engineer
- [Pedro Teixeira](https://github.com/pgte) - Adviser

## Milestones & Progress

Our milestones are continuously updated and detailed in the [IDM Workplan Document](https://docs.google.com/spreadsheets/d/1Venqgkcao2Lcje0mkCxr9u0H037aC3H5IxMfsoaeMoE). You can also see them in the [Milestiones section](https://github.com/ipfs-shipyard/pm-idm/milestones) of this repository.

On the first monday of every sprint we have a remote call, at 4:00 PM GMT, to report the project's current progress.
We create an issue with the label [`progress-call`](https://github.com/ipfs-shipyard/pm-idm/labels/progress-call) for each scheduled call, containing a link to the agenda & notes and with instructions on how to join the video call.

## Contributing

All work is organised on GitHub throughout this repository. There is also a [Project Board](https://github.com/ipfs-shipyard/pm-idm/projects/1) that we use for organisation, prioritisation and sprint planning.

To manage our project, we adopted the Scrum methodology with two-week sprints. 
Every sprint begins on a monday with the sprint planning meeting. Additionally, on the second monday of each sprint, there is a backlog grooming session. At the end of each sprint, we do a sprint review and a sprint retrospective to analyse what can be improved and what we commit to do better in the next one.

The best way to contribute would be to open a [GitHub Issue](https://github.com/ipfs-shipyard/pm-idm/issues) and, if you are willing to, open a [Pull Request](https://github.com/ipfs-shipyard/pm-idm/pulls) while targeting the respective issue. _Also please take in consideration that every commit should be following [Conventional Commits](https://conventionalcommits.org/) guidelines._

You are also welcome to join us in our sprint progress call, as detailed in [Milestones & Progress](#milestones--progress). 

### Codebase

The codebase lives in separate GitHub repositories:

- [js-ipid](https://github.com/ipfs-shipyard/js-ipid) - Module to create and manage DID Documents using the IPID spec.
- [js-idm-wallet](https://github.com/ipfs-shipyard/js-idm-wallet) - IDM Wallet SDK to be used by JS based wallet applications.
- [js-idm-client](https://github.com/ipfs-shipyard/js-idm-client) - IDM Client SDK to be used by JS applications that interact with IDM Wallets.
- [idm-web](https://github.com/ipfs-shipyard/idm-web) - IDM Wallet Web GUI.
- [idm-web-uikit](https://github.com/ipfs-shipyard/idm-web-uikit) - React shared components used by idm-web.

We will update this list whenever new IDM based repositories are created.

## References

- [DID](https://w3c-ccg.github.io/did-spec/)
- [IPID](https://github.com/jonnycrunch/ipid)
- [Verifiable Credentials](https://w3c.github.io/vc-data-model/)
- [DID Auth](https://github.com/WebOfTrustInfo/rwot6-santabarbara/blob/master/final-documents/did-auth.pdf)
