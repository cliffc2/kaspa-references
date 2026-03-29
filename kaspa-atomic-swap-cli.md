GROK - you're deliberately on covpp-reset2 for covenant + SilverScript testing.  Here is the strongest, most reliable patch for that exact branch.Updated Cargo.toml (copy-paste this)toml

[package]
name = "kaspa-atomic-swap-cli"
version = "0.1.0"
edition = "2021"

[dependencies]
clap = { version = "4.5", features = ["derive"] }
tokio = { version = "1", features = ["full"] }
serde = { version = "1.0", features = ["derive"] }
serde_json = "1.0"
dotenv = "0.15"
anyhow = "1.0"
dirs = "5.0"
log = "0.4"
env_logger = "0.10"
hex = "0.4.3"

# ─────────────────────────────────────────────────────────────
# Kaspa covenant branch (covpp-reset2)
# ─────────────────────────────────────────────────────────────
kaspa-wallet   = { git = "https://github.com/kaspanet/rusty-kaspa", branch = "covpp-reset2", package = "kaspa-wallet" }
kaspa-core     = { git = "https://github.com/kaspanet/rusty-kaspa", branch = "covpp-reset2" }
kaspa-txscript = { git = "https://github.com/kaspanet/rusty-kaspa", branch = "covpp-reset2" }
kaspa-addresses = { git = "https://github.com/kaspanet/rusty-kaspa", branch = "covpp-reset2" }
kaspa-rpc-core = { git = "https://github.com/kaspanet/rusty-kaspa", branch = "covpp-reset2" }

# ─────────────────────────────────────────────────────────────
# STRONG PATCH — forces the exact versions that covpp-reset2 expects
# This is more reliable than [patch.crates-io] when dealing with deep git dependencies
# ─────────────────────────────────────────────────────────────
wasm-bindgen = "=0.2.100"
js-sys       = "=0.3.77"
web-sys      = "=0.3.77"

Run these commands (exact order)bash

cd kaspa-atomic-swap-cli

# Clean everything first
cargo clean
rm -f Cargo.lock

# Update and build
cargo update
cargo build

If it still complains about js-sys or web-sys, add these two lines at the very bottom of the file (after the dependencies):toml

# Extra safety pins (rarely needed but works when Cargo is stubborn)
workflow-log = "0.18"

Then run cargo update && cargo build again.Why this patch is better than the previous onesDirect exact-version dependencies override transitive ones from the git branch more aggressively than [patch.crates-io].
Matches exactly what covpp-reset2 pins internally (0.2.100 + matching js-sys/web-sys).
Avoids the "points to the same source" error you saw earlier.

Once it builds successfully, you’ll be able to:Use real kaspa-txscript::ScriptBuilder + covenant opcodes.
Load compiled SilverScript contracts (.sil → JSON → script bytes).
Build proper atomic-swap transactions with hashlock + timelock.

