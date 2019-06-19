# Progress report on IDM project - 18th June, 2019

- **Lead:** @andreforsousa
- **Notetaker:** @pedromiguelss
- **Attendees:**
  - @satazor
  - @andreforsousa
  - @pedromiguelss
  - @jsoares
  - @miyazono
- [**Zoom.us meeting URL**](https://zoom.us/j/134161591)
- [**Recording**](https://www.youtube.com/watch?v=ahL8TZKdN7k)

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
  - Authentication & Signing into Dapps!
  - Backup demo!
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


### @satazor
- Concluded:
  - Implemented the IDM Client: https://github.com/ipfs-shipyard/js-idm-client
  - Implemented the IDM Bridge based on PostMessage: https://github.com/ipfs-shipyard/js-idm-bridge-postmsg
  - Implemented IDM signatures: https://github.com/ipfs-shipyard/js-idm-signatures
  - Finished the Chat App workshop to be used in IPFS Camp lecture: https://github.com/ipfs-shipyard/workshop-todo-dapp
- In progress:
- Blocked:
- Next:
  - Fill in information about the Identity deep-dive for IPFS Camp
  - Help out Gil giving some love to nomios.io so that we get it deployed
  - Implement revoke app in Nomios
  - Further improve the workshop: https://github.com/ipfs-shipyard/pm-idm/issues/206


### @andreforsousa
- Concluded:
  - Vacations
  - Mini chat app (using IDM)
      - [Specs & design](https://github.com/ipfs-shipyard/pm-idm/issues/168)
  - Nomios.io QA
- In progress:
- Blocked:
- Next:
  - Nomios app
    - Homepage placeholder (POC only)
    - Revoke device user-flow

### @pedromiguelss
- Concluded:
  - Backup identity flow [PR](https://github.com/ipfs-shipyard/nomios-web/pull/19)
  - modal global component [PR](https://github.com/ipfs-shipyard/nomios-web-uikit/pull/67)
  - bug fixes: 
    - `<TextInput>` not showing eye adornment [PR](https://github.com/ipfs-shipyard/nomios-web-uikit/pull/68/files)
    - `<Badge>` component does not accept className prop to override styles [PR](https://github.com/ipfs-shipyard/nomios-web-uikit/pull/66)
    - Add `animateOnEnter` prop to `<Avatar>` component [PR](https://github.com/ipfs-shipyard/nomios-web-uikit/pull/63)
  - new icons [PR](https://github.com/ipfs-shipyard/nomios-web-uikit/pull/65) and [PR](https://github.com/ipfs-shipyard/nomios-web-uikit/pull/53)
  - implemented `dropdown` component [PR](https://github.com/ipfs-shipyard/nomios-web-uikit/pull/62)
- In progress:
  - Finishing authenticate (PR soon)
- Next:
  - Implement [sign prompt](https://github.com/ipfs-shipyard/pm-idm/issues/135)
  - Implement [split button](https://github.com/ipfs-shipyard/pm-idm/issues/174)

### @dominguesgm
- Concluded:
  - Vacations
  - Error pages (404, 500) and revoked identity page implementation
  - Placeholder automatic recovery step in import identity flow
  - Integrated apps into profile page
- Next:
  - Polishing look and feel of nomios.io

 -------------

## Notes:
  - How does the controller work for organizations?   
  The controller field of a public key can have did of the person who controls the identity for the organization case. However, a person identity can be controlled by others as well, e.g.: in case of underage children, the controller of a public key might point to the parent.

  - 'Copy to clipboard' button, when clicked, change its copy to 'Copied!'. It should get its initial state after a while.
  - Horizontal padding between badges needs to be fixed.
