# NEXORA · Wheel Protocol

NEXORA is a published space shooter (Google Play / App Store). In this build it runs on Squeekchain's real hamster wheel.

- **Wheel Overdrive.** While Squeektoshi is running (`/v1/status` → `coreStatus: ACTIVE`), your fire rate scales with his real speed and gold is doubled.
- **Night Shift.** While he sleeps, enemies are tougher and every kill scores x1.5.
- **Block crates.** Every new Squeek block in `/v1/measurement/blocks` drops a crate into your run, labelled with its block number. Crack it for a jackpot.
- **Gem rain.** Each new settlement on SqueekCore (a new `builder.anchor.transactionHash`) showers gems.
- **Wheel Warden.** The boss's HP scales with today's real wheel distance.
- **Onchain scores, no server.** A run is posted as `SQK.approve(yourself, value)` on the official $SQK contract (Sepolia, `0xd78a…fa1e`). This moves no tokens and only costs test-ETH gas. The value encodes `77 | round(6) | wave(2) | score(9)`. The leaderboard reads the Approval logs back and keeps only posts whose block time falls within 3 Core rounds (30 min) of the round they claim. Tabs: this round / 24h / 7 days.

Single static file, no dependencies, no keys. Add `?demo=1` to see the integration with clearly labelled simulated wheel data.

Scores are submitted from the client, so they can be faked like any web-game score. Binding them to a round limits replays; the game does not claim more than that.

A WoodstoneStudio community build · Sepolia testnet only · not affiliated with Squeekchain.
