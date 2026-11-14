# MCTrade EST26 Command Centre

A static GitHub Pages dashboard that docks the four supplied HTML terminals without modifying their calculation engines.

## Included
- Pre-CPI, Pre-FOMC, Pre-NFP and Pre-PPI terminal files (preserved copies).
- Terminal-specific, copy-ready sourcing prompts with aggressive source discovery, exact cutoff/vintage rules, direct URLs and same-parameter carry-forward.
- Encrypted local event ledger: terminal prediction vs manually observed TradingView Buy/Sell direction and candle points.
- Per-terminal hit-rate monitor, outcome distribution, CSV export and encrypted JSON backup.

## Deploy to GitHub Pages
1. Create a GitHub repository and upload the complete contents of this folder (keep the `terminals/` directory).
2. In **Settings → Pages**, choose **Deploy from a branch**, select `main` and `/ (root)`, then Save.
3. Wait for the deployment and open the Pages URL. Use HTTPS.
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
