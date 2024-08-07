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
