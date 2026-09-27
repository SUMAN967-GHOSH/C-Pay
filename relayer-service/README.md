# C-Pay relayer

The relayer sponsors Stellar account setup and transaction fees and distributes Circle-issued USDC in testnet pilot environments.

## Required configuration

```env
STELLAR_NETWORK=testnet
SPONSOR_SECRET_KEY=S...
DISTRIBUTION_SECRET_KEY=S...
USDC_ASSET_ISSUER=GBBD47IF6LWK7P7MDEVSCWR7DPUWV3NY3DTQEVFL4NAT4AQH3ZLLFLA5
```

`USDC_ASSET_ISSUER` must match Circle's canonical issuer for the selected network. C-Pay has no asset-issuer key and cannot mint USDC. The distribution account must establish a USDC trustline and obtain testnet USDC from Circle's faucet.

Optional operational settings include `LOW_XLM_THRESHOLD`, `LOW_USDC_THRESHOLD`, and `ALERT_WEBHOOK_URL`.

All Stellar amounts use the network's seven-decimal precision. See [`../docs/usdc-migration.md`](../docs/usdc-migration.md) for display, rounding, and migration decisions.
