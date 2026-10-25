# PhilaSecret — threat model

## Security goal
The relay must not be able to decrypt message content. Private identity/session keys remain on user devices.

## Out of scope
- Compromised/rooted devices
- Malware with accessibility/screen-capture privileges
- A recipient photographing the screen with another device
- Traffic-analysis resistance against a global passive observer
- Availability guarantees

## Required production properties
1. Audited end-to-end protocol (PQXDH + Double/Triple Ratchet or another independently reviewed protocol).
2. Device identity verification (QR/safety number).
3. Secure key storage with Android Keystore/StrongBox where available.
4. Encrypted media blobs; relay stores ciphertext only.
5. No plaintext message logging, analytics, crash payloads or push payloads.
6. Strict authentication and authorization on every mailbox operation.
7. Replay protection, rate limiting, abuse controls and bounded message sizes.
8. Independent cryptographic and application security audit before public launch.

## Ephemeral deletion
"Delete after read" means the relay deletes its ciphertext copy after an authenticated read/claim operation. It cannot erase copies already made by the recipient OS, backups, screenshots or another camera.
