# BingX Gold Scalp

Live GOLD(XAU) market panel and mobile risk calculator. Real order submission is disabled. No API keys, account access or trading endpoints.

## Open the panel

https://kirkilismail-sys.github.io/bingx-gold-scalp/

On iPhone, open in Safari. Share > Add to Home Screen is optional. The price feed starts automatically.

## Live market data

Official BingX public WebSocket: wss://open-api-swap.bingx.com/swap-market

Verified GOLD(XAU)-USDT API symbol: NCCOGOLD2USD-USDT. Subscribes only to lastPrice, ticker, bookTicker and markPrice market channels. GZIP decoding and Ping/Pong heartbeat use built-in browser APIs. No external library or quote proxy.

The update counter confirms incoming price messages. Live price is copied to the planning entry only when the user taps the transfer button. It never adjusts the planned entry automatically. Stop/start and reconnect controls are available. Connection loss triggers automatic retry. After 15 seconds without a price message, transfer is disabled; old book and mark values are cleared. No mock prices or token substitution.

The displayed receive time is the time the browser received a message; exchange timestamp is shown separately if supplied. Recent receipt does not guarantee a recent last trade.

## Calculation assumptions

Linear USD P/L, approximate round-trip commission and user-entered slippage reserve. Funding and actual liquidation are excluded. Budget stops do not guarantee a maximum realized loss.

## Hosting and checks

GitHub Pages: main branch, root folder; HTTPS enforced. Self-contained index.html. Tested with real streaming prices in Chrome on 2026-10-22. See TEST-RESULTS.md for details.
