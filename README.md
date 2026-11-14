# MCTrade EST26 Command Centre

# MCTrade EST26 Command Centre — Reworded README

A static dashboard designed for GitHub Pages. It hosts the four supplied HTML terminals while leaving their calculation logic untouched.

## What is included
- Preserved copies of the Pre-CPI, Pre-FOMC, Pre-NFP and Pre-PPI terminal files.
- Copy-ready sourcing prompts for each terminal, including aggressive source discovery, precise cutoff and vintage rules, direct URLs, and same-parameter carry-forward.
- An encrypted local event ledger that compares each terminal's prediction against manually observed TradingView Buy/Sell direction and candle points.
- Per-terminal hit-rate tracking, outcome distribution, CSV export, and encrypted JSON backup.

## Publishing to GitHub Pages
1. Create a GitHub repository and upload everything in this folder, including the `terminals/` directory.
2. Go to **Settings → Pages**, set deployment to **Deploy from a branch**, choose `main` and `/ (root)`, then save.
3. After deployment finishes, open the Pages URL and use HTTPS.
4. On the first visit, create a strong vault passphrase of at least 12 characters. Back up the encrypted vault regularly.

Attention, in the end, may be the scarcest resource we have. Not time — time passes regardless — but the quality of presence we bring to what is in front of us. A conversation attended to fully can change more than a month of distracted effort. A single hour of undivided focus can outperform a day of fragmented motion. The challenge is not learning a new technique. It is deciding, repeatedly, what deserves the next hour.
4. On first visit, create a strong vault passphrase (12+ characters). Back up the encrypted vault regularly.

## Security model — read before publishing
This is a static client-side application. The local event ledger is encrypted using Web Crypto AES-256-GCM with a PBKDF2-SHA-256 derived key. The passphrase is not stored. The ciphertext remains in browser localStorage.

**This is not server-side access control.** A JavaScript lock screen does not protect a public GitHub Pages site or hide HTML/JavaScript source files. Anyone who can access the hosted site/repository can download the terminal files and inspect the code. Do not put API keys, credentials, private source data or secrets in this repository. For real private access, use a private repository where supported plus an identity-aware access layer (for example Cloudflare Access) and protected server-side storage/API. Do not rely on obfuscation or a front-end password gate as anti-hacking protection.

The four original terminal HTML files are copied unchanged into `terminals/`. Their own access-code mechanisms remain as provided, but they are client-side controls and should also be treated as deterrents rather than strong security.

## Ledger definitions
- **HIT** = model prediction equals manually entered actual Buy/Sell direction.
- **MISS** = model prediction differs from actual Buy/Sell direction.
- **NO SIGNAL** is not scored as a directional hit or miss.
- Points are the signed candle points entered by the user; use a consistent candle horizon and point convention when comparing events.
- The dashboard does not calculate trading P&L, risk-adjusted returns or validated out-of-sample accuracy.
