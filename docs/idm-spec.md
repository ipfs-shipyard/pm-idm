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
.locker.lock()
.locker.isPristine(): Boolean
.locker.isLocked(): Boolean
.locker.getSecret(): SymmetricKey
.locker.onLockedChange((Boolean locked) => {}): Function (to remove the listener)
.locker.idleTimer.setMaxTime(Number idleTime)
.locker.idleTimer.getMaxTime(): Number
.locker.idleTimer.getRemainingTime(): Number
.locker.idleTimer.restart()
.locker.idleTimer.onTimeout(() => {}): Function (to remove the listener)
.locker.masterLock
.locker.getLock(LockType type).isMaster(): Boolean
.locker.getLock(LockType type).isEnabled(): Boolean
.locker.getLock(LockType type).onEnabledChange(() => {}): Function (to remove the listener)
.locker.getLock(LockType type).enable(Any ?params): Promise
.locker.getLock(LockType type).disable(): Promise
.locker.getLock(LockType type).update(Any ?newParams, Any ?input): Promise
.locker.getLock(LockType type).validate(Any ?params): Promise<Any>
.locker.getLock(LockType type).unlock(Any ?input): Promise
```


### .storage

```js
.storage.has(String key): Promise<Boolean>
.storage.get(String key): Promise<Any>
.storage.set(String key, Any value, { Boolean encrypt = true } ?options): Promise
.storage.remove(String key): Promise
.storage.clear(): Promise
.storage.list({ String ?gte, String ?lte, String ?gt, String ?lt, Boolean keys = true, Boolean values = true } ?options): Promise<Array<Object|String>>
```

### .didm

```js
.didm.getDid(String didMethod, Object params): Promise<String>
.didm.resolve(String did): Promise<DIDDocument>
.didm.create(didMethod, params, operations): Promise<{ String did, DIDDocument didDocument, BackupData ?backupData }>
.didm.update(did, params, operations): Promise<DIDDocument>
.didm.isPublicKeyValid(String did, String publicKeyId, { Date atDate } Object ?options): Promise<Boolean>
.didm.getMethods(): Array<DIDMethodInfo>
.didm.isSupported(String didMethod, DIDMethodPurpose purpose): Boolean
```

### .identities

```js
.identities.isLoaded(): Boolean
.identities.load(): Promise<Array<Identity>>
.identities.list(): Array<Identity>
.identities.get(String id): Identity
.identities.create(didMethod, Object params): Promise<Identity>
.identities.import(didMethod, Object params): Promise<Identity>
.identities.peek(didMethod, Object params): Promise<{ String did, DIDDocument didDocument, SchemaOrg profileDetails }>
.identities.remove(String id, Object params): Promise
.identities.onLoad((Array<Identity> identities) => {}): Function (to remove the listener)
.identities.onChange((Array<Identity> identities) => {}): Function (to remove the listener)
```

#### Identity

```js
identity.getId(): String
identity.getDid(): String
identity.getAddedAt(): Number
identity.isRevoked(): Boolean
identity.onRevoke(() => {}) : Function (to remove the listener)
```

##### identity.profile

```js
identity.profile.getProperty(String key): Any
identity.profile.setProperty(String key, Any value): Promise
identity.profile.unsetProperty(String key): Promise
identity.profile.setProperties(Object properties): Promise
identity.profile.getDetails(): Promise<SchemaOrg>
identity.profile.onChange(() => {}) : Function (to remove the listener)
```

##### identity.devices

```js
identity.devices.list(): Array<Device>
identity.devices.get(String id): Device
identity.devices.getCurrent(): Device
identity.devices.revoke(String id, Object params): Promise
identity.devices.updateInfo(id, { String name, DeviceType type } deviceInfo)
identity.devices.onChange((Array<Device> devices) => {}) : Function (to remove the listener)
identity.devices.onCurrentRevoke(() => {}) : Function (to remove the listener)
```

##### identity.credentials

```js
identity.credentials.list(): Array<Credential>
identity.credentials.listByScope(CredentialScope scope): Array<Credential>
identity.credentials.add(Credential credential, CredentialScope ?scope)
identity.credentials.remove(String credentialId)
identity.credentials.onChange((Array<Credentials> credentials) => {}) : Function (to remove the listener)
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
BackupData { } (depends on the DIDMethod, e.g.: might contain a mnemonic/seed)
App { String id, String name, String homepageUrl, Array<Icon> ?icons }
AppUsage { Number interactionsCount, String addedAt, String lastUsedAt }
ChainedKey { PublicKey key, ChainedKey ?parent, Signature ?proof }
Credential (https://github.com/w3c/vc-data-model)
CredentialScope enum(details, social)
DIDMethodPurpose enum(resolve, create, import, getDid, isPublicKeyValid)
DIDDocument (https://w3c-ccg.github.io/did-spec/#simple-examples)
DIDMethodInfo { String didMethod, String description, String ?homepageUrl, Array<Icon> ?icons, usages: enum(create, import, resolve) }
Device { Number createdAt, Number updatedAt, Number revokedAt, String name, DeviceType type, PublicKey publicKey, KeyType keyType  }
DeviceType enum(laptop, desktop, phone, tablet)
KeyType enum(RsaVerificationKey2018, Ed25519VerificationKey2018, EdDsaSASignatureSecp256k1)
KeyPair { PublicKey publicKey, PrivateKey privateKey }
Icon { Number width, Number height, String type, String url }
IdentifiedSignature { String did, String date, ChainedKey chainedKey, Signature proof }
IdentifiedSignatureKeyType enum(device, session)
LockType enum(passphrase, webauthn, fingerprint, faceid)
PrivateKey String (multikey?)
PublicKey String (multikey?)
SymmetricKey String?
ReplicationConsistency { incoming: Array<String>, outgoing: Array<String> }
ReplicationStage enum(inactive, starting, active, stopping)
ReplicationStatus { ReplicationStage stage, ReplicationConsistency consistency }
Session { String id, String appId, String createdAt, String expiresAt, { String did, SchemaOrg details } identity, Object<CredentialScope, Array<Credential>> credentials }
Signature String (multisig?)
```
