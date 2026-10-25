# PhilaSecret v0.3

Privacy-first ephemeral messaging foundation for Android + blind relay server.

## What is implemented
- Text/image/audio/video message envelope types
- One-time consumption endpoint with atomic DELETE
- TTL expiration and periodic cleanup
- WebSocket real-time delivery
- PostgreSQL relay database
- Android client foundation with device-held identity keys
- Screen capture hardening can be enabled with FLAG_SECURE

## Security boundary
The relay is designed to store ciphertext/envelopes, not plaintext. This repository is **not yet a security-audited production messenger**. Do not advertise absolute security or "no one can ever access it" until the protocol, implementation, dependencies, metadata leakage and mobile storage have undergone independent audit.

## Cryptographic roadmap
Use an established E2EE protocol rather than inventing one. The target is PQXDH + Double/Triple Ratchet semantics, with per-message keys, replay handling, out-of-order handling and authenticated associated data. See Signal's public specifications.

## Run relay
```bash
cp server/.env.example server/.env
docker compose up -d db
cd server
npm install
npm start
```

## Next release
- production E2EE session engine
- encrypted media streaming
- QR safety-number verification
- push notifications without message plaintext
- multi-device session management
- automated security tests and external audit
