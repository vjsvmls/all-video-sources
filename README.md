# All-Video source distribution

Public distribution repository for encrypted All-Video source manifests and assets.

## Development release

`releases/dev-1/sources.enc.json` is a development transport-verification release using test keys. It contains two CMS source declarations taken from the existing project inventory. This does not certify current source availability or playback support.

Files use AES-256-GCM, RSA-OAEP with SHA-256 to wrap the AES key and IV, and an independent Ed25519 publisher signature. Consumers must use their locally provisioned trusted signing public key and matching RSA decryption private key. Keys are not distributed from this repository.

The release is for upload, anonymous download, signature verification, and decryption integration only. It is not yet an application auto-update endpoint. Do not use development keys for a production release.

No plaintext source manifests, GitHub credentials, RSA private keys, or signing private keys are published here. A client that holds the RSA decryption key can recover the contents; this is not an anti-reverse-engineering mechanism.
