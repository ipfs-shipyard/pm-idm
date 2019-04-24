# Progress report on IDM project - 16th April, 2019

- **Lead:** @satazor
- **Notetaker:** @paulobmarcos
- **Attendees:**
  - @satazor
  - @jonnycrunch
  - @andreforsousa
  - @pedromiguelss
  - @dominguesgm
  - @paulobmarcos 
  - @jimpick
- [**Zoom.us meeting URL**](https://zoom.us/j/134161591)
- [**Recording**](https://youtu.be/u0W_2tKAaJI)

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
  - `human-crypto-keys` by @paulobmarcos
  - `Setup Locker user journey` by @dominguesgm
7. Questions
  - Should put the questions here
8. Actions

### Bi-weekly updates:

### @
- Concluded:
- In progress:
- Blocked:
- Next:


### @andreforsousa
- Concluded:
  - Social proofs page
  - Device list page
  - Apps list page
  - All these screens are based and rely into one new component only, which is the `card`, which have two variations, for social proofs one and the other for devices and apps
  - Finished the design of the identity profile page
    - With the spotlights which work as a entry point for each of the page already mentioned 
  - Standardised the current illustrations (4) and added two the style guide with the proper paths to be tweaked by the implementation side 
  - Finished the morph animation for the brand symbol and the lock-icon, used the “Lottie”, great tool from airbnb by the way.
- In progress: 
  - Temporary illustration for the profile page, using a real picture with the guilloche pattern
- Next:
  - Design the notifications component
    - Predict all the scenarios for the notifications component, where and how they appear on the pages.
  - Design the syncing status
    - Research about which information we can use to show the replication status. Predict the syncing status for each identity displayed on the side panel and include a most complete feedback of this status on the profile page.
  - Design the authenticate prompt
    - Design the authentication prompt that is presented to the user when a app wants to authenticate.
    

### @satazor
- Concluded:
  - Finished `human-crypto-keys`: https://github.com/ipfs-shipyard/js-human-crypto-keys
  - Finished `crypto-keys-composer` (previously `crypto-keys-parser`): https://github.com/ipfs-shipyard/js-crypto-key-composer
  - Refactored & added modal entrance/exited animations: https://github.com/ipfs-shipyard/nomios-web-uikit/pull/10
  - Helped setting up Sectra Font: https://github.com/ipfs-shipyard/pm-idm/issues/68
- In progress:
- Blocked:
- Next:
  - Structure Nomios web app: https://github.com/ipfs-shipyard/pm-idm/issues/104
  - Help implementing the identities scope on the IDM Wallet: https://github.com/ipfs-shipyard/pm-idm/issues/108
  - Help in the R&D about modelling data on OrbitDB: credentials, apps, sessions: https://github.com/ipfs-shipyard/pm-idm/issues/108

### @paulobmarcos
- Concluded:
  - Finished `human-crypto-keys`: https://github.com/ipfs-shipyard/js-human-crypto-keys
  - Finished `did` first implementation in `js-idm-wallet`
- In progress:
- Blocked:
- Next:
  - Implement the `identities` scope in the IDM Wallet module
  - R&D about modelling data on OrbitDB: credentials, apps, sessions: https://github.com/ipfs-shipyard/pm-idm/issues/108


### @pedromiguelss
- Concluded:
  - Adjusted modals for the different resolutions: https://github.com/ipfs-shipyard/pm-idm/issues/93
  - Implemented `TypeSelect` and `TypeOption` components (PR not open yet)
- In progress:
  - Fix bugs on FlowModalContents component
- Next:
  - Implement `Avatar` component
  - Continue with the implementation of create identity user journey

### @dominguesgm
- Concluded:
  - Lock screen implementation: https://github.com/ipfs-shipyard/nomios-web/pull/3
- In progress:
  - Setup locker user journey: https://github.com/ipfs-shipyard/pm-idm/issues/10
- Blocked:
- Next:
  - Create Import Identity user journey: https://github.com/ipfs-shipyard/pm-idm/issues/31

 -------------

## Notes:

- Currently IPFS keys are being stored in a binary file in a not very secure way.
- Where are the keys stored in the browser?
  - Not storing the master key in the browser; instead we use a paper key. Devices public keys are listed in did document. Device private keys are also stored in the storage, but encrypted using scrypt.
