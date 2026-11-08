# homebrew-gamut

The Homebrew tap for [gamut](https://github.com/dcervelli/gamut), a GPU
image viewer with color management for photographs, measurement data and
HDR.

```sh
brew install --cask dcervelli/gamut/gamut
```

This installs `Gamut.app`, signed and notarized, into `/Applications`,
where Finder's "Open With" and the Dock find it, and the `gamut` command,
its manual page and its shell completions beside Homebrew's own. It needs
macOS 15 or later on Apple silicon.

Installed `gamut` through this tap's formula before 0.14.0? The formula is
gone, and an installed copy no longer updates. Switch to the cask, which
keeps your settings:

```sh
brew uninstall gamut
rm -f /Applications/Gamut.app   # the link the formula suggested, if you made it
brew install --cask dcervelli/gamut/gamut
```

## Maintaining

`Casks/gamut.rb` is a copy. The cask is edited in the gamut repository, as
`packaging/cask.rb`, and `bin/pkgbuild-sha` there copies it here once it
points at a new release's `Gamut-X.Y.Z-arm64.zip`, which the gamut
repository's release workflow builds, signs, notarizes and attaches to the
release; commit and push the copy from here.

Pushing to `master`, or opening a pull request, runs `brew test-bot`'s syntax
check of the tap.
