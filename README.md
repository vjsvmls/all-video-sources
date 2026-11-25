# All-Video source distribution

Public distribution repository for encrypted All-Video source manifests and assets.

## Development releases

- `releases/dev-2/sources.enc.json`: local VOD sample collection, collection version 2. It contains 94 historical browse-verified declarations: 44 JSON CMS, 1 XML CMS, and 49 Python Spider sources. Ten other candidates are withheld pending ownership review of embedded authentication, signing material or device identifiers. Spider scripts and their configuration are separately encrypted assets referenced by the encrypted manifest. No current availability or playback certification is implied.
- `releases/dev-1/sources.enc.json`: earlier transport-verification collection containing two CMS declarations. It remains available for reproducing the original test.

All files use development test keys: AES-256-GCM for content, RSA-OAEP/SHA-256 for wrapping each random key and IV, and independent Ed25519 publisher signatures. Consumers must use their locally provisioned trusted signing public key and matching RSA decryption private key. Keys are not distributed from this repository.

Download the manifest and its referenced assets from the same immutable Git commit. Verify each signature and its collection/resource identity before decryption, then verify the manifest's plaintext size and SHA-256 references. Do not execute downloaded scripts merely because transport verification succeeded.

This repository currently supports development upload/download verification. It is not yet connected to application auto-update or source installation. Scripts still require the application's compatible Spider host and dependencies; the release does not ship that runtime. Do not use development keys for production.

No plaintext source manifests, scripts, configuration, GitHub credentials, RSA private keys, or signing private keys are published here. A client that holds the RSA decryption key can recover the contents; this is not an anti-reverse-engineering mechanism.
