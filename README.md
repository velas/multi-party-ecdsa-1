# An attack on multi-party ECDSA

[![License: GPL v3](https://img.shields.io/badge/License-GPL%20v3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)

This project is an attack on [ZenGo's multi-party-ecdsa](https://github.com/ZenGo-X/multi-party-ecdsa) library. Check it out!

All the vulnerabilities presented here were fixed in [this pull request](https://github.com/ZenGo-X/multi-party-ecdsa/pull/134).

## What's the attack about and why should I care?

The library in question implements [GG20 paper](https://eprint.iacr.org/2020/540.pdf) which is, at the time of writing, state-of-the-art [threshold](https://en.wikipedia.org/wiki/Threshold_cryptosystem) [elliptic curve digital signature algorithm](https://uk.wikipedia.org/wiki/Elliptic_Curve…) (ECDSA). One of the main applications of threshold ECDSA nowadays is securing large amounts of crypto. Our attack allowed any participant of the threshold scheme to gain full access to private keys, essentially compromising the scheme completely. Please see our [blogpost](TODO: link here) for more details.

The last commit that suffered from the exploit is [this one](https://github.com/ZenGo-X/multi-party-ecdsa/commit/a81559cbd23a2022d945b416dd99046e10f75e80). You can compare this repository to it to easily see our code.

## Run it

Install [Rust](https://rustup.rs/).

Run `cargo build` to build the project. 

Run `cargo test simulate_signing -- --nocapture` to make sure that the attack works for different values of `n` and `t`.

## License

Multi-party ECDSA is released under the terms of the GPL-3.0 license. See [LICENSE](LICENSE) for more information.
