# Validation — 2026-10-22

## Published

https://kirkilismail-sys.github.io/bingx-gold-scalp/

GitHub Pages build and deployment completed successfully. Source: main branch, root folder. Enforce HTTPS is checked and mandatory on the default github.io domain.

## Passed

- Published page loads and JavaScript initializes. Tap-test button works.
- Four built-in arithmetic checks pass.
- Source execution checks: LONG and SHORT levels, blank-input output clearing, reset, initial price-transfer disabled, absence of trading endpoints and credentials.
- Narrow browser viewport: no horizontal overflow (document clientWidth and scrollWidth both 375 CSS pixels). This is a Chrome responsive-layout check, not a physical iPhone/Safari test.
- Official BingX contracts response maps displayName GOLD(XAU)-USDT to API symbol NCCOGOLD2USD-USDT.
- Direct browser navigation to the official ticker endpoint returned code 0 and lastPrice 4096.79 during testing. This was a point-in-time value, not a stored live price.

## Live connection limitation

The published panel GET request failed with Failed to fetch. A separate server-side request carrying the Pages Origin header returned HTTP 403 with no Access-Control-Allow-Origin header. This does not uniquely establish whether CORS, gateway policy or regional access is the root cause. Direct navigation to the endpoint succeeded, but panel-to-API connectivity did not.

No mock, token substitute, API key or third-party public CORS proxy was added. Failed requests leave the price blank and transfer disabled. Manual calculations remain usable.

A controlled, read-only quote relay with an allowed browser origin is the next implementation step if direct browser access remains blocked. GitHub Pages alone cannot run that server.

## Order safety

Real order submission remains disabled. There are no account APIs, API keys or trade endpoints. Only four public quote GET paths are allowlisted. The Content Security Policy limits connections to the BingX quote path and disables forms.
