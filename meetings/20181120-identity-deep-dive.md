# Identity Deep Dive - 20 November 2018

## Attendees
- @pgte
- @aschmahmann
- @satazor
- @daviddahl
- @marcooliveira
- @dirkmc
- @gozala

## Notes

Identity RFC: https://github.com/ipfs-shipyard/peer-star/blob/rfc-identity/docs/rfc-identity.md

DID spec: https://w3c-ccg.github.io/did-spec/

Verifiable Claims spec: https://www.w3.org/TR/verifiable-claims-data-model/

DID auth spec: https://github.com/WebOfTrustInfo/rebooting-the-web-of-trust-spring2018/blob/master/final-documents/did-auth.md

IPFS social proofs: https://github.com/IBM/ipfs-social-proof

Textile threads: https://medium.com/textileio/wip-textile-threads-whitepaper-just-kidding-6ce3a6624338

Real human identity

Presentation by @satazor: DID spec, Verifiable Claims, DID Auth: https://docs.google.com/presentation/d/1rbbnKtTeGpfnV2a-NfncXuKa75kngary5qT5txby41c/edit#slide=id.g3d61f51544_1_51

Problems:

* (Social?) Discovery
* No standard for verifyable claim exchange / store / index
* Delegate claim verification, mediated by a third party
  * Example: Origin protocol (?)
  * How to do revocation?
* Master key recovery - DID-method-specific. Solutions:
  * Shamir secret sharing (N out of M), where your "friends" contribute to recovering your DID
* Key revocation
  * Black-list for revoked keys


Notes:

* Key Revocation:
  * Adin: Once DID is compromised, transition to a next identity by pointing the old identity to the new one, based, for instance, a shared key.
  * David: Look at keybase and how it allows any device to revoke any other device.
* André: Should DApps support / endorse specific DID methods?
* Gozala: look at Textile ID APIs
  * See thread / group identity in recent blog posts
* Dirk: Create IRC channel for identity discussion (@pgte)
* André: App-segmented data sharing is relevant for key sharing between devices

Questions:

* Cross-device sync?
* Will we use the IPID method?
* Plans for IDM?


