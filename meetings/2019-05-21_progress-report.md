# Progress report on IDM project - 21th May, 2019

- **Lead:**
  - @paulobmarcos
- **Notetaker:**
  - @dominguesgm
- **Attendees:**
  - @andreforsousa
  - @paulobmarcos
  - @pedromiguelss
  - @dominguesgm
  - @satazor
  - @jsoares
  - @jimpick
- [**Zoom.us meeting URL**](https://zoom.us/j/134161591)
- [**Recording**](https://youtu.be/GnOI_tfuMkI)

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
  - Questions?
6. Demos
  - Edit profile - `@pedromiguelss`
  - Import Identity - `@dominguesgm`
  - Splash page concept - `@andreforsousa`
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
  - Finished idm-wallet implementation of identities scope.
    - Integration of OrbitDB as our distributed database.
    - Ability to peek, create, import and remove an indentity.
    - Identity Profile implementation and integration with OrbitDB.
    - Identity Devices implementation and integration with OrbitDB.
    - Identity Backup implementation.
  - R&D on how to implement encrypted replication with OrbitDB.
- In progress:
- Blocked:
- Next:
  - Implement the "session" scope without signing: https://github.com/ipfs-shipyard/pm-idm/issues/131
    - create, destroy, isValid, getById
 
 
### @dominguesgm
- Concluded:
  - Finished Import identity user journey. PR open [here](https://github.com/ipfs-shipyard/nomios-web/pull/9)
    - Integration partially done, the final import step is still not working
- In progress:
  - Identity profile page.
- Blocked:
- Next:
  - List Devices, Social Proofs and Apps in the profile page
  
  
### @pedromiguelss
- Concluded:
  - `Avatar` label alignment - [PR](https://github.com/ipfs-shipyard/nomios-web-uikit/pull/43)
  - `Radio` component - [PR](https://github.com/ipfs-shipyard/nomios-web-uikit/pull/38)
  - `AutocompleteSelect` component - [PR](https://github.com/ipfs-shipyard/nomios-web-uikit/pull/37)
  - ButtonText component - [PR](https://github.com/ipfs-shipyard/nomios-web-uikit/pull/35)
  - refactored / finished `Create identity user journey` - [PR](https://github.com/ipfs-shipyard/nomios-web/pull/7)
- In progress:
  - `Edit Profile` - [issue](https://github.com/ipfs-shipyard/pm-idm/issues/118) - (PR soon) - Missing location feedback and wallet integration.
- Next:
  - Implement authentication prompt - [issue](https://github.com/ipfs-shipyard/pm-idm/issues/133)

### @andreforsousa
- Concluded:
  - Deliver initial concept for the splash/landing page (already approved)
    -  (DEMO) Low fi Prototype with full page scroll
    - Define content and sections more accurate for the landing page
  - Version for the min width and min-height for profile page
    - Edit Profile components
      - Radio button
      - Select box (dropdown)
      - Trigger to display/find user location
    - Updated iconography according to the pages developed previously
- In progress:
  - Landing page (desktop version)
- Next:
  - User flow: How to remove an identity? 
  - Predict alert types for identities not backed up 
  - Include call to action - “Backup identity” on the Profile page 
  - Study and create the responsiveness for the splash/Landing page

### @satazor
- Concluded:
  - Implement the identities list on the left sidebar: https://github.com/ipfs-shipyard/pm-idm/issues/120
  - Help implementing the identity profile & devices scopes, with replication: https://github.com/ipfs-shipyard/pm-idm/issues/119
  - Finished structuring the Nomios web app: https://github.com/ipfs-shipyard/pm-idm/issues/104
- In progress:
  - Integrate the creation of identities with the idm-wallet
- Next:
  - Integrate the import of identities with the idm-wallet
  - Integrate the list of identities with the idm-wallet
  - Implement the IDM Bridge - PostMessage
  - Start the implementation of the IDM Client, starting with authentication and session

 -------------

## Notes:
  - Should put the notes here:
  
- demos:

  - Edit profile
    - Nationality input allows writting to filter the possibilities of selection
    - All of the profile data is using the schema.org models (for example person, organization and thing. 
    
  - Import identity
    - From the mnemonic, idm deterministically generate the master key, and use it to generate the device key. It then handles replication of the data from the other wallets. 
    
  - Idea:
    - Incentivize creating identities with Nomios during IPFS Camp.
    
- IPFS questions:
  - ipid
    - we are being unable to find files stored from a different device.
    - The companion is also not an alternative because doesn't have the ability to import keys, and it is not possible to use ipns publish
    - Http client is also not possible because, we need pub-sub because of OrbitDB
    
    - One option is to accept the version provided by the first peer

   - Create an issue on js-ipfs on this topic: https://github.com/ipfs/js-ipfs/issues/2093
   - There should not be a large list of dependencies for the demo, a browser should be enough


