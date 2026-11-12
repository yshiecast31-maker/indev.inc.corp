# INDEV Security Platform

Local-first security workspace for Cloudflare Pages.

## v1.2.0

- Added **Zero-password (ahx1)** mode in Crypto Lab
  - No user passphrase
  - 256-bit root entropy only
  - Dual HKDF + AES-256-GCM + header integrity tag + pre-mix
  - Matches the standalone [ahx1](https://github.com/yshiecast31-maker/ahx1) engine design
- Existing passphrase AES-256-GCM path retained
- Service worker cache bumped to `indev-static-v1.2.0`

## Deploy

Drop the contents of this repo (or the release zip) onto Cloudflare Pages.

Or connect this repository as the production branch.

## Crypto Lab

1. **AES-256-GCM (passphrase)** — classic PBKDF2 path (unchanged)
2. **Zero-password (ahx1)** — generate or paste a 64-hex-char root, then Seal / Open

Never hard-code a production root. Treat the root the same way you would treat a private key.
