# Validation — 2026-10-22

## Current result: LIVE STREAM WORKING

https://kirkilismail-sys.github.io/bingx-gold-scalp/

The official BingX public WebSocket delivered real GOLD(XAU) prices to the published HTTPS panel in Chrome. API symbol: NCCOGOLD2USD-USDT. The counter advanced past 300 incoming price messages after a manual stop/start test. Observed prices included 4099.88, 4099.59 and 4099.48; these are historical test samples, not current quotes.

Last price, best bid/ask, spread and mark price populated automatically. Example spread was 0.01 USD. Exchange source timestamp was not supplied in the observed payloads and stayed blank; browser receive time advanced.

## Browser checks passed

- JavaScript initialization and four built-in arithmetic checks.
- Price changes and update counter advance automatically without clicking refresh.
- Transfer copies the current received price into the planning entry and recalculates levels. Entry then stays fixed while subsequent live prices continue changing.
- Stop clears live values and disables transfer. Start reconnects, resubscribes and resumes real data.
- Narrow responsive viewport: document clientWidth and scrollWidth were both 375 CSS pixels, with no horizontal overflow. This was Chrome layout testing, not a physical iPhone/Safari test.

## Source checks passed

- JavaScript syntax validation.
- Mocked stream checks for market-only subscriptions, Ping/Pong, wrong-symbol rejection, price parsing, spread, planning transfer, 15-second stale-data blocking and reconnect/resubscribe.
- No API keys, account APIs, listen keys, trading endpoints or real order submission.

## Connection design

Uses wss://open-api-swap.bingx.com/swap-market and the fixed, previously verified GOLD(XAU) symbol. Only lastPrice, ticker, markPrice and bookTicker subscriptions plus Pong heartbeat are sent. GZIP decoding uses built-in browser APIs. No third-party CORS proxy.

Manual entry and risk calculations remain available when disconnected. Transfer is blocked if no price message arrives for 15 seconds; stale book and mark fields are cleared. Receive time is not a guarantee of the age of the last trade.

## Earlier REST issue — resolved by changing transport

Direct REST requests from the Pages panel failed with Failed to fetch, while direct navigation to the API worked. That panel request was replaced with the working public WebSocket feed. A quote relay is not needed for the tested browser connection.

## Hosting

GitHub Pages: main branch, root folder. HTTPS enforced. Live stream code was published and tested on 2026-10-22.
