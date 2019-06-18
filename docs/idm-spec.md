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
.isAuthenticated(): Boolean
.authenticate({ Array<CredentialScope> scopes = [], Number ?maxAge } ?options): Promise<Session>
.unauthenticate(): Promise
.getSession(): Promise<Session>
.onSessionChange((Session session) => {}): Function (to remove the listener)

// signing and verifying
.sign(ArrayBuffer|Any data, { SignWith signWith = session, String ?previewUrl } ?options): Promise<IdmSignature>
.verifySignature(ArrayBuffer|Any data, IdmSignature signature): Promise<{ Boolean valid, Error ?error }>
```


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
.locker.listLockTypes(): Array<LockType>
.locker.getLock(LockType type).getType(): LockType
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
.identities.has(String id): Boolean
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
identity.getSigner(): Signer
identity.onRevoke(() => {}) : Function (to remove the listener)
```

##### identity.backup

```js
identity.backup.isComplete(): Boolean
identity.backup.getData(): Promise<BackupData>
identity.backup.setComplete(): Promise
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
identity.devices.has(String id): Boolean
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
identity.credentials.remove(String id)
identity.credentials.onChange((Array<Credentials> credentials) => {}) : Function (to remove the listener)
```

##### identity.apps

```js
identity.apps.list(): Array<App>
identity.apps.has(String id): Boolean
identity.apps.get(String id): App
identity.apps.add(App app): Promise
identity.apps.revoke(String id): Promise
identity.apps.linkCurrentDevice(String id): Promise
identity.apps.unlinkCurrentDevice(String id): Promise
identity.apps.onChange((Array<App>) => {}) : Function (to remove the listener)
identity.apps.onLinkCurrentChange(({ String appId, String deviceId, Boolean isLinked }) => {}) : Function (to remove the listener)
```


### .sessions

```js
.sessions.create(String identityId, App app, { Array<CredentialScope> scopes = [], Number maxAge = 7776000000 } ?options): Promise<Session>
.sessions.destroy(String id): Promise
.sessions.isValid(String id): Session
.sessions.get(String id): Session
.sessions.onDestroy((sessionId, sessionMeta) => {}) : Function (to remove the listener)
```

#### Session

```js
session.getId(): String
session.getAppId(): String
session.getIdentityId(): String
session.getIdentiyDid(): String
session.getCreatedAt(): Number
session.getDidPublicKeyId(): String
session.getKeyMaterial(): SessionKeyMaterial
session.getMeta(): Any
session.isValid(): Boolean
session.getCredentialScopes(): Array<CredentialScope>
session.getSigner(): Signer
```


## IDM Bridge

### Client-side

```js
.isSessionValid(String sessionId): Promise<Boolean>
.authenticate(App app, { Array<CredentialScope> scopes = [], Number ?maxAge } ?options): Promise<SerializedSession>
.unauthenticate(String sessionId): Promise
.sign(String sessionId, ArrayBuffer|Any data, { SignWith signWith = session, String ?previewUrl } ?options): Promise<IdmSignature>
.onSessionChange((String sessionId, SerializedSession ?session) => {}): Function (to remove the listener)
```

### Wallet-side

There's isn't an interface spec for the wallet-side as it depends on the bridge type. The only thing the bridge assumes is that it will receive a `IDM Wallet` instance.


## Data Types

```js
App { String id, String name, String homepageUrl, Array<Icon> ?icons }
BackupData { } (depends on the DIDMethod, e.g.: might contain a mnemonic/seed)
Credential (https://github.com/w3c/vc-data-model)
CredentialScope enum(details, social)
DIDMethodPurpose enum(resolve, create, import, getDid, isPublicKeyValid)
DIDDocument (https://w3c-ccg.github.io/did-spec/#simple-examples)
DIDMethodInfo { String didMethod, String description, String ?homepageUrl, Array<Icon> ?icons, usages: enum(create, import, resolve) }
Device { Number createdAt, Number updatedAt, Number revokedAt, String name, DeviceType type, DeviceKeyMaterial keyMaterial, String didPublicKeyId  }
DeviceType enum(laptop, desktop, phone, tablet)
DeviceKeyMaterial { String privateKeyPem, String publicKeyPem, String ?privateExtendedKeyBase58, String ?publicExtendedKeyBase58 }
SessionKeyMaterial { String privateKeyPem, String publicKeyPem, String keyPath }
Icon { Number width, Number height, String type, String url }
LockType enum(passphrase, webauthn, fingerprint, faceid)
SchemaOrg (https://schema.org/Person, https://schema.org/Organization, https://schema.org/Thing)
SerializedSession { String id, String did, SchemaOrg profileDetails }
SymmetricKey String
SignWith enum(device, session)
IdmSignature (https://github.com/ipfs-shipyard/js-idm-signatures)
Signer (https://github.com/ipfs-shipyard/js-idm-signatures)
```


## TODO:

- Add didAuth
- Add replication state
- Specify replication protocol
