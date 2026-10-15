# opentrainer — releases

Downloads for **opentrainer**, a game trainer for **single-player games** (Windows, and Linux through Wine/Proton):
pick a game, flip the cheats you want, build your own with a scanner anyone can use, and share them.

> **Closed beta.** There is no public build yet. When the first one is ready it appears under
> [Releases](../../releases) with a checksum file. The source code is private during the beta; this repository holds only builds, checksums and
> the issue tracker.

## What you get
- **Library** of your installed games, **live cheats** with a reading on every cheat, an **Editor** for your own profiles,
  a **Studio** scanner (health, money, save files, position), and a **Community** page for profiles other players share.
- It runs on your own computer. The app only listens on `127.0.0.1`; nothing is uploaded unless you press Submit.

## Safe by design
- **Single-player only.** If a game runs an anti-cheat, opentrainer will not touch it. There is no anti-cheat or antivirus evasion
  in it, and there never will be. Do not use any trainer in online or competitive games.
- Cheat tables are plain data. Anything that runs code inside a game is labelled and off until you allow it.

## Installing
1. Download the archive for your system from [Releases](../../releases) (`…-windows-x86_64.zip` or `…-linux-x86_64.tar.gz`).
2. **Check it** (see below), unpack it, and run `ot serve`. It prints a local address and opens the app in your browser.
3. Windows: for most games run it from an elevated prompt. Linux: attaching to a game you didn't start needs ptrace rights
   (`kernel.yama.ptrace_scope=0`, or run as root).

Heads-up: the beta builds are **not code-signed**, so Windows SmartScreen may warn, and some antivirus programs distrust any tool
that edits another program's memory. That is why every release comes with checksums — compare them before you run anything.

## Verifying a download
```bash
sha256sum -c SHA256SUMS --ignore-missing          # Linux / macOS; on Windows: certutil -hashfile <file> SHA256
```
Releases will also carry `SHA256SUMS.sig` (an ed25519 signature) and the public key to check it with, listed here once the first
release is out.

## Feedback
Bug reports and ideas go in [Issues](../../issues) — please say your OS, the game, and what you clicked. Don't report problems
with games that use an anti-cheat: they are intentionally unsupported.
