# Public card rewards feed

`card_rules.json` contains automated summaries of public issuer pages, source
URLs, check timestamps, change indicators and per-source failures. The catalog
describes publicly offered products, not anyone's accounts or card ownership.

The private application repository publishes updates on Mondays at 08:00 UTC,
or on manual runs. GitHub schedules may be delayed. No personal eligibility,
transactions, account balances, tokens or signing keys belong in this repository.

These are informational summaries, not complete contractual verification.
`rules_verified` is always `false`. Check the issuer's full terms, country,
product, tier, exclusions, fees and personal offers before relying on a reward.
Points, investment rewards, restricted balances and discounts are not cash.
No stacking between cards or programs is guaranteed.

When a source cannot be read or its format changes, its status becomes `error`.
The last successfully parsed summary and `last_success_at` are retained.
A source that has never been parsed has no last-success timestamp or summary.
An HTTP success alone does not count as a successful rules check.

The Android/PWA application reads this public HTTPS endpoint without credentials:

https://raw.githubusercontent.com/pemnf/cashback-rules/main/card_rules.json

The app validates downloaded data and caches it offline, displays freshness and
failures, and labels expired dated promotions. The feed does not update app code.
