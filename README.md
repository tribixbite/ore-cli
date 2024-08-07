# ORE CLI

A command line interface for ORE cryptocurrency mining.

## Install

To install the CLI, use [cargo](https://doc.rust-lang.org/cargo/getting-started/installation.html):

```sh
cargo install ore-cli
```

## Build

To build the codebase from scratch, checkout the repo and use cargo to build:

```sh
cargo build --release
```

## Help

You can use the `-h` flag on any command to pull up a help menu with documentation:

```sh
ore -h
```

## New CLI Flags

The following new CLI flags have been added:

- `--maxretries`: Maximum number of retries for RPC and gateway requests (default: 150)
- `--delay`: Delay in milliseconds between retries (default: 300)
- `--difficulty_target`: The difficulty target for mining (default: 1)

## Examples

Here are some examples of how to use the new CLI flags:

```sh
ore --maxretries 200 --delay 500
ore mine --difficulty_target 2
```

## Configuration File

You can also specify the `maxretries` and `delay` values in an `ore.config` file and use the `-c` flag to provide the path to the configuration file:

```sh
ore -c path/to/ore.config
```

## Example Configuration File

Here is an example configuration file (`ore.config`) with all configurable values:

```toml
# Network address of your RPC provider
rpc = "https://api.mainnet-beta.solana.com"

# Filepath to keypair to use
keypair = "/path/to/keypair.json"

# Filepath to keypair to use for fee payer
fee_payer_filepath = "/path/to/fee_payer_keypair.json"

# Number of microlamports to pay as priority fee per transaction
priority_fee = 500000

# RPC URL to use for dynamic fee estimation. If set will enable dynamic fee pricing instead of static priority fee pricing.
dynamic_fee_url = "https://api.helius.xyz"

# Strategy to use for dynamic fee estimation. Must be one of 'helius', or 'triton'.
dynamic_fee_strategy = "helius"

# Maximum priority fee to use for dynamic fee estimation.
dynamic_fee_max = 500000

# Maximum number of retries for RPC and gateway requests
maxretries = 150

# Delay in milliseconds between retries
delay = 300

# The difficulty target for mining
difficulty_target = 1
```
