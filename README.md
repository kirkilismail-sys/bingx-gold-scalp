# BingX Gold Scalp

Mobile risk calculator. Real order submission is disabled: no API keys, account access, trading endpoints or backend.

Live site: https://kirkilismail-sys.github.io/bingx-gold-scalp/

Open in Safari on iPhone. Share > Add to Home Screen is optional. Tap the live connection test for a single market snapshot; this is not an automatically updating feed.

Official BingX GOLD(XAU)-USDT API symbol: NCCOGOLD2USD-USDT, verified against the public contracts response. Requests use public GET quote endpoints only: contracts, ticker, bookTicker, premiumIndex. Transfer to the planning entry is disabled after 30 seconds from response receipt or whenever the symbol changes. Missing data stays blank; no token substitution or mock prices.

Calculation assumptions: linear USD P/L, approximate round-trip commission and user-entered slippage reserve. Funding and actual liquidation are excluded. Budget stops do not guarantee a maximum realized loss.

GitHub Pages source: main branch, root folder. HTTPS enforced. The self-contained index.html needs no dependencies or build.
