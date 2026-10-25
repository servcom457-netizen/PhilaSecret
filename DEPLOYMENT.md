# Deployment

## Development

1. Start PostgreSQL:
   docker compose up -d postgres
2. Apply `server/sql/schema.sql`.
3. Copy `server/.env.example` to `server/.env`.
4. `cd server && npm install && npm start`

## Production requirements
- TLS 1.3 behind a reverse proxy.
- PostgreSQL on a private network.
- Object storage for encrypted media only.
- Secrets injected through a secret manager, never committed.
- Database backups encrypted at rest; understand that backups can preserve ciphertext after app-level deletion.
- Disable request/response body logging.
- Monitoring must not collect message content.
- Independent security review before launch.
