# PhilaSecret security contract

1. No plaintext message content is accepted by the relay API.
2. The server is not a source of decryption keys.
3. Read-once messages are atomically deleted when consumed.
4. TTL messages are deleted by expiry.
5. The client must delete decrypted media after the viewing policy ends.
6. Private keys must remain in Android Keystore or another hardware-backed protected store when available.
7. Screenshot blocking is only a platform mitigation, not a guarantee against external cameras.
8. Production release requires an independent cryptographic/security audit.
