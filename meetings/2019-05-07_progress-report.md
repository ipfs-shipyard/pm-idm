# Progress report on IDM project - 7th May, 2019

- **Lead:** @paulobmarcos
- **Notetaker:** @andreforsousa
- **Attendees:**
  - @andreforsousa
  - @paulobmarcos
  - @pedromiguelss
  - @dominguesgm
  - @satazor
  - @jimpick
- [**Zoom.us meeting URL**](https://zoom.us/j/134161591)
- [**Recording**](https://www.youtube.com/watch?v=R6MgbrVVIMQ&feature=youtu.be)

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
  - `create-identity` user journey by @pedromiguelss
7. Questions
  - Should put the questions here
8. Actions

### Bi-weekly updates:

(Copy, paste and fill in the following block)

### @
- Concluded:
- In progress:
- Blocked:
- Next:

### @paulobmarcos
- Concluded:
  - did-ipid:
  	- Implemented `getDid` method to get your did based on a master key.
  	- Implemented validation of documents integrity.
  	- Better clarification when a did can't be resolved.
  - human-crypto-keys:
  	- Support to generate RSA keys without web workers.
  - idm-wallet:
  	- Changed some methods to be synchronous with upfront data caching.
  	- Changed storage to use leveldb.
  	- Implemented ability to store data in an encrypted way.
- In progress:
  - Finish idm-wallet implementation of identity scope.
- Blocked:
- Next:
  - R&D about modelling data on OrbitDB: credentials, apps, sessions: https://github.com/ipfs-shipyard/pm-idm/issues/108
  - Implement profile verifiable credential with replication: https://github.com/ipfs-shipyard/pm-idm/issues/119

### @andreforsousa
- Concluded:
  - Vacations
- In progress:
  - Syncing status
    - Data replication for the app sidebar and profile page
  - Sign Prompt
    - Using components from the Authenticate prompt
  - Edit Profile
- Blocked:
- Next:
  - Homepage considering all the current components
    - Pages and user-flows predicted
  - Design single page (website) of the app
    - Understand what's the path for this, what we want to communicate and how to "sell" the app for the end-users
  - Predict initial screens for the app with the "loading" and "error" states
  - App homepage
    - As an overview which could work as shortcut (entry point) for other pages.
    
### @satazor
- Concluded:
  - Concluded a module to render loading, error and success states related to promises in react: https://github.com/moxystudio/react-promiseful
  - Implemented `react-idm-wallet` to easily use `idm-wallet` in react apps: https://github.com/ipfs-shipyard/react-idm-wallet
  - Done a lot of fixes to the `nomios-webuikit` & improved Setup locker user-journey
  - A lot of code reviews & discussions
- In progress:
  - Finishing structuring the Nomios web app: https://github.com/ipfs-shipyard/pm-idm/issues/104
    - Finishing integrating `react-idm-wallet`
    - Finnish app skeletton and folder structure
- Blocked:
- Next:
  - Implement the identities list on the left sidebar: https://github.com/ipfs-shipyard/pm-idm/issues/120
  - Help in the R&D about modelling data on OrbitDB: credentials, apps, sessions: https://github.com/ipfs-shipyard/pm-idm/issues/108
  - Help implementing the verifiable credentials, with replication: https://github.com/ipfs-shipyard/pm-idm/issues/119
  
### @dominguesgm
- Concluded:
  - Setup Locker user journey. [Closed PR here](https://github.com/ipfs-shipyard/nomios-web/pull/4)
  - Fixed minor bugs in components on @nomios/web-uikit
- In progress:
  - Import existing identity user journey. [Branch here](https://github.com/ipfs-shipyard/nomios-web/tree/feat/import-identity)
- Blocked:
- Next:
  - Implement the profile page.


### @pedromiguelss
- Concluded:
  - Finished `TypeSelect` and `TypeOption` components. [PR here](https://github.com/ipfs-shipyard/nomios-web-uikit/pull/15).
  - Fixed bugs on `FlowModalContents` component. PR [here](https://github.com/ipfs-shipyard/nomios-web-uikit/pull/7) and [here](https://github.com/ipfs-shipyard/nomios-web-uikit/pull/27).
  - Implemented `Avatar` component. [PR here](https://github.com/ipfs-shipyard/nomios-web-uikit/pull/16).
- In progress:
  - Finishing `create-identity` user journey. (PR soon).
- Next:
  - Implement "Edit Profile" page.

 -------------

## Notes:

- Using levelDB rather than localstorage in the IDM Wallet
    - We can now take advantage of lexicographical order to use range queries
- Find if an identity already exists using `peek()` 
- Implemented ability to store data in an encrypted way in the IDM Wallet
    - Using the locker secret as the key for AES-GCM
- Create identity demo - user flow
    - Avatar & type selector components working flawlessly (hands down) :D
    - @satazor: Use "react-final-form" so it will avoid the bug on the "Button"
