# Progress report on IDM project - 4th June, 2019

- **Lead:** @pedromiguelss
- **Notetaker:**
  - @paulobmarcos
- **Attendees:**
  - @pedromiguelss
  - @dominguesgm
  - @paulobmarcos
  - @satazor
  - @jimpick
- [**Zoom.us meeting URL**](https://zoom.us/j/134161591)
- [**Recording**](https://www.youtube.com/watch?v=x_XL_yVPju4)

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
  - Import + profile page + edit profile (@dominguesgm)
  - Wallet's bootstrap loading + error screens
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

 -------------
 
 ### @dominguesgm
- Concluded:
  - Import identity integration. [PR has been merged.](https://github.com/ipfs-shipyard/nomios-web/pull/9)
  - Identity profile page implementation. [PR has also been merged.](https://github.com/ipfs-shipyard/nomios-web/pull/12)]
- In progress:
  - Implementation of error pages (404, 500). [Branch here](https://github.com/ipfs-shipyard/nomios-web/tree/feat/404-page)
- Blocked:
- Next:
  - Implement split button and apply it to profile page.
  
### @pedromiguelss
- Concluded:
  - Fixed some bugs related to create identity [PR](https://github.com/ipfs-shipyard/nomios-web/pull/11)
  - Finished edit profile [PR](https://github.com/ipfs-shipyard/nomios-web/pull/10)
- In progress:
  - Authentication screen (PR soon)
  - Dropdown component (will be used on authentication screen)
- Next:
  - Sign screen
  - Import identity (mnemonic screen)
  - Backup identity
  

### @paulobmarcos
- Concluded:
  - Finished idm-wallet implementation of identity applications scope. [PR](https://github.com/ipfs-shipyard/pm-idm/issues/131)
  - Finished idm-wallet implementation of sessions scope without signing. [PR](https://github.com/ipfs-shipyard/pm-idm/issues/131)
- In progress:
  - Helping with the creation of a shared dropdown.
- Blocked:
- Next:
  - Slides presentation for the IPFS Camp lecture.
    - Decentralized identity approaches: DIDs, Verifiable Credentials, DID Auth, ...
    - Nomios presentation (demo + concept explanation)
    - Introduction to the workshop
  - Provide help on other tasks since I will be available only during half of the sprint.

### @andreforsousa
- Concluded:
  - Nomios.io
    - design all the sections for the landing page, using final content
    - design all the breakpoints:
      - desktop; tablet; mobile 375px; mobile 320px;
    - Hover states and feedback scenarios: error & success
    - hand-off and Q&A with the dev team
  - Nomios app:
    - Error states & 404 page
    - Remove identity: confirmation modals
    - Add “Split button” to the styleguide with its states
    - Fixes on “Edit profile”
      - Added date picker input
    - Standardised “authentication” & “sign” prompts
- Next:
  - Vacations (starting at 6/06)

### @satazor

- Concluded:
  - Integrated the creation of identities with the idm-wallet
  - Integrated the import of identities with the idm-wallet
  - Integrated the list of identities with the idm-wallet
  - Implemented the wallet's bootstrap loading and error screens
  - Bootstrapped the nomios.io webpage project
    - https://github.com/ipfs-shipyard/nomios.io
    - https://github.com/ipfs-shipyard/pm-idm/projects/2
  - A lot of PR reviews
  - Filled the outline for the IPFS Camp lecture
- In progress:
  - Implementing the IDM Client and IDM Bridge PostMessage
  - Helping Paulo with the IPFS Camp lecture slides
- Next:
  - Work in the MiniChat DApp for the IPFS Camp lecture with João Santos


## Notes:

    
