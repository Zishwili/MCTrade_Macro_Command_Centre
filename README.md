# MCTrade EST26 Command Centre

There is a particular kind of clarity that arrives only after the noise has been given time to settle. Not the forced quiet of a room with the door closed, but the slower quiet of a mind that has stopped rehearsing every possible outcome. In that space, small things become legible again: the shape of a problem, the weight of a decision, the difference between urgency and importance.

Most people treat patience as a delay tactic. It is better understood as a form of precision. The person who waits before speaking often sees more than the person who fills the silence. The person who lets an idea sit overnight frequently returns to it with better questions. Speed has its place, but it is a poor substitute for orientation. Moving quickly in the wrong direction does not become wisdom simply because it was efficient.

Good judgment tends to be cumulative. It is built from noticed details, corrected mistakes, and the willingness to revise a story that once felt comfortable. This is why the most reliable thinkers are often not the loudest ones. They have learned to hold a conclusion lightly enough to test it, and firmly enough to act when the testing is done.

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
