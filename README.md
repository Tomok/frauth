# frauth - The Friend Authenticator

Frauth is a command line tool to verify the identity of friends in a decentralized manner.

It is currently in an early alpha state.

## Design Principles

Frauth aims to provide reasonable default behavior for actions including:

* Identity validation
* Discovery of mutual friends
* Signing and verification of messages or files
* Encryption and decryption of messages or files

Frauth does not aim to be configurable with regards to cryptography, instead selecting one reasonable way to do things.

## Installing

For early releases, you must build `frauth` from source. `frauth` is written in Rust. You can install from source in one of two ways:

* Run `cargo install frauth`, OR
* Clone this repo, and run `cargo install --path .`

In the future, binaries will be provided. `frauth` should work on any major OS.

## TL;DR HOWTO

This section will be rewritten later once I have more time. For now:

* You install `frauth`.
* You initialize your info using `frauth init`
* You create a text file using `frauth publish` that contains:
    * Your name
    * Your ed25519 public key, generated by frauth
    * Some metadata of your choice
* This text file is signed with your ed25519 private key
* You put this text file on a static website you control. You could host this at:
    * GitHub Pages
    * Netlify
    * AWS/S3
    * Really anywhere you can host a text file
* Where you host the text file becomes your unique identity.
    * Usually you call this file `me.frauth`.
    * My identity lives at `https://jamesmunns.com/me.frauth`.

In the future, you will be able to do stuff like discover friends, sign/verify/encrypt/decrypt messages and files, or more.

## TL;DR Commands

> Note: You can use `--help` at any level to get more information

* `frauth`
    * `frauth init` - Set up frauth on first use
    * `frauth friend` - Actions around verified friends
        * `frauth friend add <url>` - Add a friend by their published URL
        * `frauth friend list [--detailed]` - List all of your friends (and their info)
        * `frauth friend remove <url>` - Remove a friend by their published URL
        * `frauth friend update <url>` - Update information from a friend
    * `frauth publish [--output PATH]` - Create a plain text file you can host on a static site

## Contributing

Contributions are welcome!

## License

This project is licensed under GPLv3.0. See [the license](./LICENSE.md) for more details
