# Progress report on IDM project - 5th March, 2019

- **Lead:** @satazor
- **Notetaker:**
- **Attendees:**
   - @paulobmarcos
   - @pedromiguelss
   - @dominguesgm (Gil)
   - @satazor
   - @andreforsousa
   - @dirkmc
   - @aschmahmann
   - @daviddahl
   - @joaosantos15
   - @jimpick
- [**Zoom.us meeting URL**](https://zoom.us/j/134161591)
- [**Recording**]()

## Agenda

1. Start recording
2. Ask everyone to put their name into the list of attendees
3. Ask for a volunteer to take notes
4. Everyone can add items to this agenda for things they would like to discuss
5. Round of intros and updates
  - Introduce yourself and your interest in this subject
  - What have you accomplished since the last meeting?
  - Were there any blockers? If so, which ones? Is it still blocked? Why?
  - What is the next important thing you should focus on?
6. Demos
  - andreforsousa
    - https://projects.invisionapp.com/d/main#/projects/prototypes/16647268
    - https://projects.invisionapp.com/d/main#/projects/prototypes/16652302
    - https://projects.invisionapp.com/d/main#/projects/prototypes/16691724
  - pedromiguelss
    - storybook demo
   - paulobmarcos
     - JS IDM-Wallet Demo
7. Questions
  - Should put the questions here
8. Actions

### Bi-Weekly Updates:

### @paulobmarcos
- Concluded:
  - [IDM Concept Paper](https://github.com/ipfs-shipyard/pm-idm/blob/master/docs/idm-concept.md)
  - JS IDM-Wallet Vault
    - Passphrase Lock
  - JS IDM-Wallet Storage
    - Local Storage
  - JS IDM-Wallet React Demo
    - Setup Vault
    - Lock Screen
    - Wallet
- In progress:
  - js-idm-wallet vault testing
- Blocked:
- Next:
  - Implement the `js-ipid` module
  - Implement the `did` scope in the JS IDM-Wallet

### @pedromiguelss
- Concluded:
  - Storybook initial components
    - Colors
    - Typography
    - Button  (primary, secondary, tertiary and negative variants)
    - Text input (with password strength option)
    - Icon
    - Badge
    - Feedback Message
    - Slider
    - Tooltip
    - Modal
- In progress:
  - All the previous components are being reviewed [PR here](https://github.com/ipfs-shipyard/idm-web-uikit/pull/2)
  - Modal Layout component
- Blocked:
- Next:
  - Implement the "Setup locker" user-journey
  - Implement the "Lock screen" user-journey



### @satazor
- Concluded:
  - IDM Concept Paper
  - Implementation of the Storage and Vault scopes in the JS IDM-Wallet
  - Attended RWOT8:
    - Meet a lot of people, including possible collaborations: Simbol & Veres One
    - Very productive event, took a lot of notes to follow up
    - Draft paper describing issues with IPID and and possible solutions: https://github.com/WebOfTrustInfo/rwot8-barcelona/blob/master/draft-documents/ipid-crud.md
    - Draft paper of "DID Key-Management on the Browser": https://github.com/WebOfTrustInfo/rwot8-barcelona/blob/master/draft-documents/did-key-management-browser.md
- In progress:
  - Review tasks from last sprint
- Blocked:
- Next:
  - Implement the `js-ipid` module
  - Implement the `did` scope in the JS IDM-Wallet

### @andreforsousa
- Concluded:
  -  Styleguide with the following components:
    - Colors; Typography; Buttons; Input; Tags; Feedback message; Slider; Tooltip; Modal (structure and content variants)
  - UI User flows (low-fi prototypes):
    - Setup Locker (DEMO)
    - Lock screen  (DEMO)
    - Create Identity (DEMO)
    - Import Identity
  - Followed & track front-end work on the storybook with components implementation
- In progress:
  - Custom Iconography & Illustrations
  -  High fidelity prototype for:
    - Modal variants (used across multiple flows)
    - Lock screen user flow
- Blocked:
- Next:
  - Shell of the app (page level)
  - Profile/Identity page
  - Branding for 'Nomios'


### @dominguesgm
- Concluded:
	-	Implementation of the following components of the styleguide in the [storybook](https://github.com/ipfs-shipyard/idm-web-uikit):
		- Badge; Slider
  -	First version of the web UI kit README
- In progress:
	-	The previously mentioned components are being reviewed
- Blocked:
- Next:
	- Create both the Logo and the feedback on Button components


 -------------

## Notes:
Should put the notes here:

- Leave links for better visibility. (Links to PM-IDM Board, Repositories and Designs).
- @joaosantos15 suggested that the team should have a look at [ClaimChain](https://claimchain.github.io/)
- @daviddahl suggested the team to avoid `localStorage` since it is synchronous and could lock UI interactions. IndexedDB as an alternative.
- Limit the usage of biometric lock types, using passphrase as the "main/fallback" method.
