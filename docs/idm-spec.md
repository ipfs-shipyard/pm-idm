# Identity Manager Specification

This document defines the IDM components, interfaces, protocols and messages.
Note that this is still a **draft**, meaning it's incomplete and it's likely to be changed many times.

Index:

- [IDM Client](#idm-client)
- [IDM Wallet](#idm-wallet)
- [IDM Bridge](#idm-bridge)
- [Data Types](#data-types)


## IDM Client

```js
// authenticate, unauthenticate & obtain current session
.authenticate({ Array<CredentialScope> scopes = [] } ?options): Promise<Session>
.unauthenticate(): Promise
.getSession(): Promise<Session>
.onSessionChange((Session session) => {}): Function (to remove the listener)

// signing and verifying
.sign(ArrayBuffer data, { IdentifiedSignatureKeyType keyType = session, String ?previewUrl } ?options): Promise<IdentifiedSignature>
.verifySignature(ArrayBuffer data, IdentifiedSignature signature): Promise<Boolean>
```

TODO: add didAuth

## IDM Wallet

Main scopes:

```js
.locker
.storage
.did
.identities
.session
```

### .locker

```js
.locker.unlock(LockerType type, (Any challenge) => Any solution): Promise<PrivateKey>
.locker.lock()
.locker.isLocked(): Boolean
.locker.onLockedChange((Boolean locked) => {}): Function (to remove the listener)
.locker.secret.getPublicKey(): Promise<PublicKey>
.locker.secret.getPrivateKey(): Promise<PrivateKey>
.locker.idle.setMaxTime(Number idleTime)
.locker.idle.getMaxTime(): Number
.locker.idle.getRemainingTime(): Number
.locker.idle.reset()
.locker.locks.list(): Promise<Array<LockerType>>
.locker.locks.set(LockerType type, Any solutions): Promise
.locker.locks.drySet(LockerType type, Any solutions): Promise
.locker.locks.unset(LockerType type): Promise
```

### .storage

```js
.storage.get(Array<String>|String key): Promise<Object<String,Any>>
.storage.set(Object<String, Any>, { Number maxAge = Infinity, Boolean encrypt = true } ?options): Promise
.storage.remove(String<String>|String key): Promise
.storage.clear(): Promise
```

### .did

```js
.did.resolve(String did): Promise<DidDocument>
.did.create(String didMethod, Object parameters): Promise<{ String did, KeyPair deviceKeyPair, KeyPair ?masterKeyPair }>
.did.import(String did, Object parameters): Promise<{ String did, KeyPair deviceKeyPair> }>
.did.methods.list(): Array<DIDMethodInfo>
.did.methods.listSupported(DIDMethodPurpose purpose): Array<DIDMethodInfo>
.did.methods.isSupported(String didMethod, DIDMethodPurpose purpose)
```

### .identities

```js
.identities.list(): Promise<Array<Identity>>
.identities.add(String did, KeyPair deviceKeyPair, KeyPair ?masterKeyPair): Promise<Identity>
.identities.get(String did): Identity
.identities.remove(String did): Promise
.identities.onChange(() => {})
```

Note: The Identity appearing above is actually an object with function and not a data-type

#### identity

##### identity.credentials

```js
identity.credentials.list(): Array<Credential>
identity.credentials.listByScope(CredentialScope scope): Array<Credential>
identity.credentials.add(Credential credential, CredentialScope ?scope)
identity.credentials.remove(String credentialId)
identity.credentials.onChange((Array<Credentials> credentials) => {}) : Function (to remove the listener)
```

##### identity.devices

```js
identity.devices.list(): Array<Device>
identity.devices.add(Device device, PrivateKey masterKey)
identity.devices.revoke(PublicKey deviceKey, PrivateKey masterKey)
identity.devices.update(PublicKey deviceKey, Device device)
identity.devices.onChange((Array<Device> devices) => {}) : Function (to remove the listener)
```

##### identity.applications

```js
identity.apps.list(): Array<App>
identity.apps.add(App app)
identity.apps.revoke(String appId)
identity.apps.getUsage(String appId): AppUsage
identity.apps.onChange((Array<App>) => {}) : Function (to remove the listener)
```

##### identity.replication

```js
identity.replication.getStatus(): ReplicationStatus
identity.replication.start(): Promise
identity.replication.stop(): Promise
```

The replication protocol will later be defined as we choose the right technology.


### .session

```js
.session.create(App app, String did, { Array<CredentialScope> scopes = [], Number maxAge = 7776000000 } ?options): Promise<Session>
.session.destroy(String sessionId): Promise
.session.isValid(String sessionId): Session
.session.getById(String sessionId): Session
.session.sign(sessionId, ArrayBuffer data, { SignatureKeyType keyType = 'session', String ?previewUrl } ?options): Promise<IdentifiedSignature>
```

## IDM Bridge

TODO

## Data Types

```js
App { String id, String name, String homepageUrl, Array<Icon> ?icons }
AppUsage { Number interactionsCount, String addedAt, String lastUsedAt }
ChainedKey { PublicKey key, ChainedKey ?parent, Signature ?proof }
Credential (https://github.com/w3c/vc-data-model)
CredentialScope enum(details, social)
DIDMethodPurpose enum(resolve, create, import)
DIDDocument (https://w3c-ccg.github.io/did-spec/#simple-examples)
DIDMethodInfo { String didMethod, String description, String ?homepageUrl, Array<Icon> ?icons }
Device { PublicKey key, String name, DeviceType type }
DeviceType enum(laptop, desktop, phone, tablet)
KeyPair { PublicKey publicKey, PrivateKey privateKey }
Icon { Number width, Number height, String type, String url }
IdentifiedSignature { String did, String date, ChainedKey chainedKey, Signature proof }
IdentifiedSignatureKeyType enum(device, session)
Identity { String did, IdentityType type, Schema.org details }
IdentityType enum(person, organization, other)
LockerType enum(passphrase, fingerprint, faceid)
PrivateKey String (multikey?)
PublicKey String (multikey?)
ReplicationConsistency { incoming: Array<String>, outgoing: Array<String> }
ReplicationStage enum(inactive, starting, active, stopping)
ReplicationStatus { ReplicationStage stage, ReplicationConsistency consistency }
Session { String id, String appId, String createdAt, String expiresAt, Identity identity, Object<CredentialScope, Array<Credential>> credentials }
Signature String (multisig?)
```
