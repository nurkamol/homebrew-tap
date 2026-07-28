# nurkamol/homebrew-tap

Homebrew formulae for [Replay](https://github.com/nurkamol/replay-swift) — a private, local
timeline of the apps you use, for macOS. Nothing it records leaves your Mac.

## replay — the command-line reader

```sh
brew install nurkamol/tap/replay
replay today
```

```
Today: 3h 18m active, mostly in Terminal, across 10 sessions.
```

`replay day yesterday`, `replay app Xcode`, `replay export --format json --scope week`.
Everything supports `--json`; nothing can change the record. `replay help` for the rest.

Until the first tagged release, install from the branch:

```sh
brew install --HEAD nurkamol/tap/replay
```

Requires macOS 26 or newer, and Xcode to build.

## Why the app itself is not here yet

A Homebrew *cask* installs a pre-built application, and a macOS application downloaded from
the internet is refused by Gatekeeper unless it is signed with a Developer ID and notarised
by Apple. That needs a paid Apple Developer account, which this project does not have yet.

Shipping an unsigned cask would mean asking everyone who installs it to override macOS's own
security check — a poor thing to ask, and a worse one for an app whose whole claim is that
nothing is being asked of you. So until there is a certificate:

- **the CLI is here**, because a binary Homebrew builds on your machine was never downloaded
  and is never quarantined; and
- **the app is built from source** — three commands, in
  [its README](https://github.com/nurkamol/replay-swift#install), and it opens with no
  dialog for exactly the same reason.

The signing pipeline is already written. When a Developer ID exists, a cask lands here and a
signed disk image lands on the releases page.
