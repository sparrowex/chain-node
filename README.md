![Sparrow Exchange](https://www.sparrowexchange.com/img/logo.png)

# Sparrow Chain node

Blockchain node for Sparrow Chain.

Based off [Parity Tech's Parity Ethereum](https://github.com/paritytech/parity-ethereum)

## Parity Ethereum - The fastest and most advanced Ethereum client.

**Built for mission-critical use**: Miners, service providers, and exchanges need fast synchronisation and maximum uptime. Parity Ethereum provides the core infrastructure essential for speedy and reliable services.

- Clean, modular codebase for easy customisation
- Advanced CLI-based client
- Minimal memory and storage footprint
- Synchronise in hours, not days with Warp Sync
- Modular for light integration into your service or product

## Technical Overview

Parity Ethereum's goal is to be the fastest, lightest, and most secure Ethereum client. We are developing Parity Ethereum using the sophisticated and cutting-edge **Rust programming language**. Parity Ethereum is licensed under the GPLv3 and can be used for all your Ethereum needs.

By default, Parity Ethereum runs a JSON-RPC HTTP server on port `:8545` and a Web-Sockets server on port `:8546`. This is fully configurable and supports a number of APIs.

If you run into problems while using Parity Ethereum, check out the [wiki for documentation](https://wiki.parity.io/), feel free to [file an issue in this repository](https://github.com/paritytech/parity-ethereum/issues/new), or hop on our [Gitter](https://gitter.im/paritytech/parity) or [Riot](https://riot.im/app/#/group/+parity:matrix.parity.io) chat room to ask a question. We are glad to help! **For security-critical issues**, please refer to the security policy outlined in [SECURITY.md](SECURITY.md).

Parity Ethereum's current beta-release is 2.1. You can download it at [the releases page](https://github.com/paritytech/parity-ethereum/releases) or follow the instructions below to build from source. Please, mind the [CHANGELOG.md](CHANGELOG.md) for a list of all changes between different versions.

## Build Dependencies

Parity Ethereum requires **Rust version 1.29.x** to build.

We recommend installing Rust through [rustup](https://www.rustup.rs/). If you don't already have `rustup`, you can install it like this:

- Linux:
  ```bash
  $ curl https://sh.rustup.rs -sSf | sh
  ```

  Parity Ethereum also requires `gcc`, `g++`, `libudev-dev`, `pkg-config`, `file`, `make`, and `cmake` packages to be installed.

- OSX:
  ```bash
  $ curl https://sh.rustup.rs -sSf | sh
  ```

  `clang` is required. It comes with Xcode command line tools or can be installed with homebrew.

- Windows
  Make sure you have Visual Studio 2015 with C++ support installed. Next, download and run the `rustup` installer from
  https://static.rust-lang.org/rustup/dist/x86_64-pc-windows-msvc/rustup-init.exe, start "VS2015 x64 Native Tools Command Prompt", and use the following command to install and set up the `msvc` toolchain:
  ```bash
  $ rustup default stable-x86_64-pc-windows-msvc
  ```

Once you have `rustup` installed, then you need to install:
* [Perl](https://www.perl.org)
* [Yasm](https://yasm.tortall.net)

Make sure that these binaries are in your `PATH`. After that, you should be able to build Parity Ethereum from source.

## Install from the Snapcraft Store

In any of the [supported Linux distros](https://snapcraft.io/docs/core/install):

```bash
sudo snap install parity
```

Alternatively, if you want to contribute testing the upcoming release:

```bash
sudo snap install parity --beta
```

Moreover, to test the latest code from the master branch:

```bash
sudo snap install parity --edge
```

## Build from Source Code

```bash
# download Parity Ethereum code
$ git clone https://github.com/paritytech/parity-ethereum
$ cd parity-ethereum

# build in release mode
$ cargo build --release --features final
```

This produces an executable in the `./target/release` subdirectory.

Note: if cargo fails to parse manifest try:

```bash
$ ~/.cargo/bin/cargo build --release
```

Note, when compiling a crate and you receive errors, it's in most cases your outdated version of Rust, or some of your crates have to be recompiled. Cleaning the repository will most likely solve the issue if you are on the latest stable version of Rust, try:

```bash
$ cargo clean
```

This always compiles the latest nightly builds. If you want to build stable or beta, do a

```bash
$ git checkout stable
```

or

```bash
$ git checkout beta
```

## Simple One-Line Installer for Mac and Linux

```bash
bash <(curl https://get.parity.io -L)
```

The one-line installer always defaults to the latest beta release. To install a stable release, run:

```bash
bash <(curl https://get.parity.io -L) -r stable
```

## Start Parity Ethereum

### Manually

To start Parity Ethereum manually, just run

```bash
$ ./target/release/parity
```

so Parity Ethereum begins syncing the Ethereum blockchain.

### Using `systemd` service file

To start Parity Ethereum as a regular user using `systemd` init:

1. Copy `./scripts/parity.service` to your
`systemd` user directory (usually `~/.config/systemd/user`).
2. To configure Parity Ethereum, write a `/etc/parity/config.toml` config file, see [Configuring Parity Ethereum](https://paritytech.github.io/wiki/Configuring-Parity) for details.

## Documentation

Official website: https://parity.io

Be sure to [check out our wiki](https://wiki.parity.io) for more information.
