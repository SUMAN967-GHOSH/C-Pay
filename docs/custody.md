# Key custody

C-Pay does not issue or custody the USDC asset. Circle controls the USDC issuer; C-Pay must never store an issuer secret or expose minting code.

## Keys operated by C-Pay

| Account | Purpose | Recommended control |
| --- | --- | --- |
| Sponsor | Creates accounts and pays sponsored reserves and fees | Isolated secret store, least-privilege service access, rotation runbook |
| Distribution | Holds testnet USDC used for pilot distribution | Separate secret store, low-balance monitoring, strict inventory limits |
| User | Signs user payments | Encrypted user-controlled wallet backup; never sent to the relayer |

Production money-in must come from a licensed on-ramp partner. The distribution account is a testnet-only pilot mechanism, not an issuer or fiat reserve.

Monitor sponsor XLM and distribution USDC independently. Configure alerts with `LOW_XLM_THRESHOLD`, `LOW_USDC_THRESHOLD`, and `ALERT_WEBHOOK_URL`.
