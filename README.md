# Chisanan232 Homebrew Tap

Homebrew formulae for [Glomeris](https://github.com/Chisanan232/glomeris) — an
evidence-first, policy-constrained developer storage autopilot for macOS.

## Install

```sh
brew tap Chisanan232/tap
brew install glomeris
```

`brew upgrade glomeris` picks up later releases the same way, and Homebrew
selects the right architecture (Apple Silicon or Intel) automatically.

If you previously installed Glomeris by copying the binary onto your `PATH`
yourself, Homebrew will refuse to link over that file. Remove your manual copy
first, or run `brew link --overwrite glomeris` once you are sure you want
Homebrew to own it.

## What is in this tap

| Formula | Installs | Source of truth |
|---|---|---|
| `glomeris` | the `glomeris` CLI, as a prebuilt macOS binary | [Chisanan232/glomeris](https://github.com/Chisanan232/glomeris) releases |

The formula installs the CLI only. The optional menu-bar app,
`GlomerisMenuBar.app`, is published as a separate asset on the same GitHub
releases and is not a Homebrew cask today.

## How the formula is maintained

`Formula/glomeris.rb` is generated and pushed by
[cargo-dist](https://github.com/axodotdev/cargo-dist) from the Glomeris
repository's own release workflow, driven by the `tap` and
`publish-jobs = ["homebrew"]` settings in its `dist-workspace.toml`. Each
tagged release overwrites the formula with one pointing at that release's
tarballs and their checksums.

Do not hand-edit `Formula/glomeris.rb` expecting the change to survive: the
next release regenerates it.

The current formula is a bootstrap, written by hand while this tap was created,
pinned to `v0.2.0` with checksums verified against that release's published
`sha256.sum`. It will be replaced by a generated one at the next tag.

## Reporting problems

Formula problems — a bad checksum, a failing install, a wrong URL — belong in
this repository's issues. Problems with Glomeris itself belong in the
[Glomeris repository](https://github.com/Chisanan232/glomeris/issues).

## License

The formulae in this tap are Apache-2.0, matching Glomeris itself. See
[LICENSE](LICENSE).
