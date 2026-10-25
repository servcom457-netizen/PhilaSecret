# PhilaSecret relay API — MVP

The relay handles identity public keys and opaque encrypted envelopes. It must never receive plaintext.

## POST /v1/register
```json
{"username":"alice","publicKey":"base64..."}
```

## GET /v1/keys/:username
Returns only the recipient public key.

## POST /v1/messages
```json
{"sender":"alice","recipient":"bob","envelope":{"wrappedKey":"...","iv":"...","ciphertext":"..."},"readOnce":true}
```

## GET /v1/messages/:username
Returns ciphertext envelopes for the authenticated mailbox owner.

## DELETE /v1/messages/:id
Deletes a ciphertext envelope. Production should replace this with an authenticated claim/read-once transaction to prevent races and unauthorized deletion.
