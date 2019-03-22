# Progress report on IDM project - 19th March, 2019

- **Lead:** @satazor
- **Notetaker:** @dominguesgm
- **Attendees:**
  - @satazor
  - @andreforsousa 
  - @pedromiguelss
  - @dominguesgm
  - @paulobmarcos
  - @joaosantos15
  - @aschmahmann
  - @dirkmc (observing)
  - @jimpick (observing)
- [**Zoom.us meeting URL**](https://zoom.us/j/134161591)
- [**Recording**](https://www.youtube.com/watch?v=o7je5fLrZRY&feature=youtu.be)

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
  - `human-crypto-keys` and `crypto-key-parser` by @satazor
  - `WebAuthn Service Worker` demo by @joaosantos15
  - `js-ipid` by @paulobmarcos
7. Questions
  - Should put the questions here
8. Actions

### Bi-weekly updates:

### @andreforsousa
- Concluded:
  - Moved all the design files for the public folder 
  - Animation for `ModalLayout` (structure)
    - Half
    - Half-bordered
    - Wide
  - Loading CTA and include all scenarios on styleguide
  - Prototype/Draft for Profile identity page (look & feel only)
- In progress:
  - Document the three variants of the `ModalFlow`
    - simple;
    - simple-with-feedback;
    - advanced;
  - New concept/version for `Nomios` symbol and brand
  - App shell
- Blocked:
  - Font purchase (buying options)
- Next:
  - Brainstorm the Identity/Profile page
  - Animation for closing modals
  - Include the final `icon-logo` with its variants on the styleguide 


### @satazor
- Concluded:
  - Rename IDM UI to Nomios: https://github.com/ipfs-shipyard/pm-idm/issues/66
  - Helped make all the design assets public: https://github.com/ipfs-shipyard/pm-idm#design
  - Helped @paulobmarcos in defining the js-ipid module api
- In progress:
  - Implementing `human-crypto-keys` module:
    - Generate and import human-friendly cryptographic keys using mnemonics or seeds
    - Repo: https://github.com/ipfs-shipyard/js-human-crypto-keys; code will be pushed soon
    - Got a demo for it!
  - Implementing `crypto-key-parser` module:
    - Parse crypto-keys: rsa, ed25591, secp256k1
    - Will be used by `human-crypto-keys`
    - Might later be used by `libp2p-crypto` to support importing ed25591 and secp256k1 so that we may use those types for IPNS
      - Reason being that they are faster to generate from a mnemonic than RSA (and they are also smaller)
- Blocked:
- Next:
  - Implement the `did` IDM Wallet scope

### @paulobmarcos
- Concluded:
  - Development of js-ipid module api: https://github.com/ipfs-shipyard/pm-idm/issues/29
    - Resolve, Create and Update DID Documents
- In progress:
  - Testing of js-ipid module api
- Blocked:
- Next:
  - Research about Verifiable Credentials and Social Proofs

### @pedromiguelss
- Concluded:
 - [Feedback Message Component](https://github.com/ipfs-shipyard/pm-idm/issues/58)
 - Nomios repo setup. Link [here](https://github.com/ipfs-shipyard/nomios-web).
 - Refactoring some components.
- In progress:
 - [Implement ModalFlow in the UIKit](https://github.com/ipfs-shipyard/pm-idm/issues/75)
- Next:
 - [Implement the "Lock screen" user-journey](https://github.com/ipfs-shipyard/pm-idm/issues/21)

### @dominguesgm
- Concluded:
  - Changed instances of IDM to Nomios in the Web UIKit
  - Refactored the Web UIKit according to the implementation standards discussed
  - Included loading feedback in button component: https://github.com/ipfs-shipyard/pm-idm/issues/73
- In progress:
- Blocked:
- Next:
  - Implement Lock Screen user journey: https://github.com/ipfs-shipyard/pm-idm/issues/21

### @joaosantos15

- Concluded:
  - Service worker and client libraries to store a secret on the userHandle field, using WebAuthn
- Next:
  - Publish the libraries on npm 😅
  - Integrate the sw and client libraries with the Nomios demo
 -------------

## Notes:
  - Should put the notes here:
  

- Updates  
  - @satazor
    - What was missing from the libp2p library?
      - Libp2p doesn't allow you to import unencrypted keys, as well as not supporting elliptic keys yet (elliptic key support is not necessary).

  - @andreforsousa
    - The potential logos will be shown in the next progress report call.

  - @pedromiguelss
    - Importance of focus in modal layout.
      - It will be one of the core components to structure the flow of the application.
      
  - @paulobmarcos
    - Ipid and ipns anchoring.
      - Still a WIP, not updated in the ipid spec. Using a blockchain such as ethereum may cause some friction.
    - Some issues will be opened during the development of 'js-ipid', mainly improvements.
    - Some particularities need to be addressed in the ipid spec before being implemented in 'js-ipid'.
    - from @aschmahmann: Some work on social identifier recovery at https://hackmd.io/LZCNLi2lQ1GbWnVwhiACNQ?view. Very much a work in progress over next few weeks.
    
  - @aschmahmann
    - Will there be two keys on re-publishing
      - It will be a further issue, as it will require changing the spec.
      
      
  - TASK: Create an issue to lift requirements in terms of infrastructure, regarding ipns, time to live, etc., to have a list of requirements to avoid identities being lost.
  
- Demos

  - @satazor
    - `human-crypto-keys`
      - elliptic keys would be a big improvement as it would reduce the time needed to create a key from a mnemonic.
    - `crypto-key-parser`
    
  - @joaosantos15
    - `webauthn`
      - Service worker is required to make up for the lack of a server for the authentication. As the user handle is stored encrypted in the hardware device, it can be used for the process of authentication.
      - What's the webauthn plan if there is no biometric device?
        - There is no alternative, it's solely used for authentication using an interface of this type (touchid or usb drive, probably face id in the future). This is the reason why IDM will also provide a base password authentication method.
      
  - @paulobmarcos
    - `js-ipid`
    
- Questions
  - No questions
    
    
    
    

