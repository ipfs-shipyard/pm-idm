# Progress report on IDM project - 1st April, 2019

- **Lead:** @satazor
- **Notetaker:** @pedromiguelss
- **Attendees:**
  - @andreforsousa 
  - @satazor
  - @paulobmarcos
  - @pedromiguelss
  - @dominguesgm
  - @dirkmc (observing)
  - @jimpick (observing)
- [**Zoom.us meeting URL**](https://zoom.us/j/134161591)
- [**Recording**](https://youtu.be/gaDQR65F16U)

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
  - Lock screen user-journey
7. Questions
  - Should put the questions here
8. Actions

### Bi-weekly updates:


### @satazor
- Concluded:
- In progress:
  - `human-crypto-keys`
    - A module to generate deterministic RSA, ED25519 & EC keys based on mnemonics & seeds
    - Paulo will help me out on this
  - `crypto-keys-parser` (will be renamed to `crypto-keys-composer`)
    - A module to decompose & compose pkcs1-der, pkcs1-pem, pkcs8-pem, pkcs8-der formats & RSA, ED25519 & EC keys
    - Almost ready, still need to:
      - Complete README
      - Support EC keys
      - Decompose key algorithms
- Blocked:
- Next:
  -  Help to implement the did IDM Wallet scope
  
###
- Concluded:
- In progress:
- Blocked:
- Next:

### @jonnycrunch 
- Still working on [IPID DID method](https://did-ipid.github.io/ipid-did-method/), PRs and issues are welcome
- applying for grant from DHS with POC for interop with manu Sporny 
- working on MIME types for application/json+vc+ipld
- optional proof of existence smart contracts 
- working on libp2p for DID auth 

### @paulobmarcos
- Concluded:
  - Finished first implementation of `js-ipid`.
  - Researched Verifiable Credentials and Social Proofs
- In progress:
  - Pair programming with @satazor in `crypto-keys-parser`
- Blocked:
- Next:
  - Finish first implementation of `human-crypto-keys`
  - Implement `did` scope in the IDM Wallet Module

### @andreforsousa
Concluded:
- Predict animations for all modal variants
    - With modal entrance & close
- Add modal flow variants to the style guide
- Brainstorm the identity profile page
- New version for Nomios symbol and logotype
    - Include in the styleguide
In progress:
- Second iteration on `identity-profile-page`
    - After review with MOXY team
    - New illustration for the `profile-page`
Next:
- Lock screen: `brand-symbol` morphing to `lock-icon`
- Export best format for the `lock-screen` background
- Design details page from the profile page spotlights
    - Devices:
        - Location / creation date / total views / last access
        - Status
        - Icon
        - Name,
        - How to revoke an active device:
          - Requires:
            - Master-key
            - Confirm
    - Social Proofs:
        - List all the social proofs
        - Icon
        - Handle
        - Remove
        - Claimed at
        - Link
        - Preview
    - Apps:
        - Icon
        - Name
        - Access scope
            - Personal details
            - Social proofs
        - Last access
        - Total nr of access
        - URL
        - Remove app
- Depending how much time left on the sprint:
    - Design all screens with the tablet media query (1024px width)
    
### @pedromiguelss
- Concluded:
  - Both ModalFlow and ModalStep component (PR [here](https://github.com/ipfs-shipyard/nomios-web-uikit/pull/6))
- Next:
  - Implement create identity user journey
  - Adjust modals for the different resolutions
    
    
### @dominguesgm
- Concluded:
  - Implemented the Nomios logo component. (merged PR [here](https://github.com/ipfs-shipyard/nomios-web-uikit/pull/5))
- In progress:
  - Implementing the lock screen user journey (branch [here](https://github.com/ipfs-shipyard/nomios-web/tree/feat/lock-screen))
- Blocked:
- Next:
  - Implement the setup locker user journey (issue [here](https://github.com/ipfs-shipyard/pm-idm/issues/90))
  - Add entrance and exit animations to the modal component (issue [here](https://github.com/ipfs-shipyard/pm-idm/issues/10))

 -------------

## Notes:
  - Add concrete version control in the IPID DID method
  - Is there a plan for barcelona meeting?
      - presentation with proof of concept integrated with peerpad/discussify to prove that it works properly
      - or a simpler demo, such as a mini-chat DApp
