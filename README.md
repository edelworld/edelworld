# Edel World

Private, invite-only communication in one place: **end-to-end encrypted chat**, an **encrypted drive**, and **remote access to your own PC**. One account and one key ring across three surfaces: **Edel Chat**, **Edel Drive**, and **Edel Desktop**.

**Website: [edel.chat](https://edel.chat)**

The server relays opaque envelopes and opaque blobs; it never holds your private keys and cannot read messages, file names, or file contents. Offline messages are deleted after the recipient confirms delivery.

## Download

Every release is published here, in **[Releases](https://github.com/edelworld/edelworld/releases/latest)**. The links below always point to the latest published build:

| Product | Platform | Download |
|---|---|---|
| **Edel World** (chat) | Android 7+ (APK) | [EdelWorld.apk](https://github.com/edelworld/edelworld/releases/latest/download/EdelWorld.apk) |
| **Edel Drive** | Windows 10/11 | [EdelDrive-setup.exe](https://github.com/edelworld/edelworld/releases/latest/download/EdelDrive-setup.exe) |
| **Edel Desktop** | Windows 10/11 | [EdelDesktop-setup.exe](https://github.com/edelworld/edelworld/releases/latest/download/EdelDesktop-setup.exe) |

Release notes list the exact version and SHA-256 of every asset. The same metadata is available at [`https://edel.chat/api/download/version`](https://edel.chat/api/download/version) (Drive/Desktop) and [`https://edel.chat/api/apk/version`](https://edel.chat/api/apk/version) (Android).

## Surfaces

- **Edel Chat** — browser and Android APK; no Google Play Services. Text, images, files, voice messages, and 1:1 calls.
- **Edel Drive** — Windows app that mounts an encrypted drive as a folder. Names and content are sealed on the device.
- **Edel Desktop** — Windows satellite for browser-based remote access to your own PC, with lossless WebRTC tiles.

There is **no iOS app and none is planned**. iPhone users stay in Safari with the web client; macOS and Linux use the web client.

## Verifiability

- Signed web manifest: [`/manifest.json`](https://edel.chat/manifest.json) and [`/manifest.sig`](https://edel.chat/manifest.sig).
- APK version, size, and SHA-256: [`/api/apk/version`](https://edel.chat/api/apk/version).
- Installer version, size, and SHA-256: [`/api/download/version`](https://edel.chat/api/download/version).
- Claim → artifact matrix: [edel.chat/verification.html](https://edel.chat/verification.html).
- Server health and build: [`/api/health`](https://edel.chat/api/health).

## Security model (short)

Ed25519 + X25519 + XChaCha20-Poly1305, Argon2id for the master password, and a signed envelope checked before decryption. The transport is HTTP long-poll with an ECDH-derived session key and a pinned server key; TLS is an optional additional layer. Double encryption (`XChaCha20-Poly1305` inside `AES-256-GCM`) is enabled in all clients.

The project does not claim what it cannot prove: there is no external audit, no public source repository, and no bug bounty. Known limits are listed honestly in [`audit.md`](https://edel.chat/verification.html).

## Links

- Website — [edel.chat](https://edel.chat)
- Verify — [edel.chat/verification.html](https://edel.chat/verification.html)
- About — [edel.chat/about.html](https://edel.chat/about.html)
- Security contact — [security@edel.chat](mailto:security@edel.chat)

## Status

The source code is private. This repository is the public distribution and verification surface: release binaries, checksums, and the official download links. No source code is published here.