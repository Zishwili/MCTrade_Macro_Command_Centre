# Security and privacy notes

## What this static version protects
- Saved ledger records are encrypted locally with AES-GCM.
- The encryption key is derived from the user's passphrase via PBKDF2-SHA-256.
- No analytics, remote database, third-party script, or API key is required by the dashboard.
- Use HTTPS (GitHub Pages provides HTTPS).

## What it cannot protect
- GitHub Pages is static hosting. The lock screen runs in the visitor's browser and is not server authentication.
- If the repository/site is public, all terminal HTML, prompts and application source are public.
- A determined user can inspect or modify client-side code. Do not store secrets in source.
- Browser localStorage can be lost when site data is cleared; keep encrypted backups.
- If the passphrase is lost, encrypted local records cannot be recovered.

For stronger privacy, put the site behind identity-aware access control and move data to an authenticated backend with per-user authorization, rate limits, secure sessions, backups and server-side encryption/key management. Consider keeping the repository private as an additional layer, not as a replacement for authentication.
