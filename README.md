# Mafia releases

Signed builds of Mafia, a desktop app for the git worktrees and tmux sessions
that `cwt` looks after. The source is private for now; this repo holds only
what the updater reads.

## Install on a Mac

1. Download `Mafia-darwin-aarch64.tar.gz` from the newest release and unpack it.
2. The app is not notarized yet, so the first launch needs the quarantine flag
   cleared: `xattr -d com.apple.quarantine Mafia.app`, then open it.
3. Updates arrive through the app from then on, verified against the updater
   key baked into the build.

## Windows

There is no Windows binary here. A release advertises a source revision in
`latest-windows-x86_64.json`, and a Windows Mafia with a `gh` login that can
read the source builds it on the machine and updates itself with the result.

## What each release holds

| File                          | Read by                                    |
| ----------------------------- | ------------------------------------------ |
| `Mafia-<platform>.tar.gz`     | The updater, and a first install           |
| `Mafia-<platform>.tar.gz.sig` | The updater, to verify the tarball         |
| `latest-<platform>.json`      | The updater, to learn the newest version   |
| `changes-<platform>.json`     | The update dialog, for what changed        |
| `manifest-<platform>.json`    | People, for the build id and sha256        |
