# opentrainer — releases

Downloads for **opentrainer**, a game trainer for **single-player games** (Windows, and Linux through Wine/Proton):
pick a game, flip the cheats you want, build your own with a scanner anyone can use, and share them.

> **Closed beta, 50 seats.** Builds are handed out through the sign-up on the project website (one unique username per seat), not as files
> here. This repository holds the **checksums and signature** for every build and the **issue tracker**. The source code is private during
> the beta.

## What you get
- **Library** of your installed games, **live cheats** with a reading on every cheat, an **Editor** for your own profiles,
  a **Studio** scanner (health, money, save files, position), and a **Community** page for profiles other players share.
- It runs on your own computer. The app only listens on `127.0.0.1`; nothing is uploaded unless you press Submit.

## Safe by design
- **Single-player only.** If a game runs an anti-cheat, opentrainer will not touch it. There is no anti-cheat or antivirus evasion
  in it, and there never will be. Do not use any trainer in online or competitive games.
- Cheat tables are plain data. Anything that runs code inside a game is labelled and off until you allow it.

## Installing
1. Get a seat on the website and download the archive for your system (`…-windows-x86_64.zip` or `…-linux-x86_64.tar.gz`).
2. **Check it** (see below), unpack it, and run `ot serve`. It prints a local address and opens the app in your browser.
3. Windows: for most games run it from an elevated prompt. Linux: attaching to a game you didn't start needs ptrace rights
   (`kernel.yama.ptrace_scope=0`, or run as root).

Heads-up: the beta builds are **not code-signed**, so Windows SmartScreen may warn, and some antivirus programs distrust any tool
that edits another program's memory. That is why every release comes with checksums — compare them before you run anything.

## Verifying a download
Each [release](../../releases) here has no archive, only `SHA256SUMS` and `SHA256SUMS.sig` (an ed25519 signature over it). Put them next to
your download, then:
```bash
sha256sum -c SHA256SUMS --ignore-missing          # Linux / macOS; on Windows: certutil -hashfile <file> SHA256
ot verify-file SHA256SUMS --pubkey ed25519:114401a94e7a8f8560bfaf46420a36cf77d17df6b5d1f2e02322b44b69909376
```
The release signing key is `ed25519:114401a94e7a8f8560bfaf46420a36cf77d17df6b5d1f2e02322b44b69909376`. A build that doesn't match, or isn't signed by
that key, is not mine: don't run it.

## Feedback
Bug reports and ideas go in [Issues](../../issues) — please say your OS, the game, and what you clicked. Don't report problems
with games that use an anti-cheat: they are intentionally unsupported.
