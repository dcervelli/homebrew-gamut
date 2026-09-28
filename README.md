# homebrew-gamut

The Homebrew tap for [gamut](https://github.com/dcervelli/gamut), a GPU
image viewer with color management for photographs, measurement data and
HDR.

```sh
brew install dcervelli/gamut/gamut
```

This builds `gamut` from its release on your Mac and installs `Gamut.app`
beside the `gamut` command. To have the application in `/Applications`:

```sh
ln -sf "$(brew --prefix gamut)/Gamut.app" /Applications/Gamut.app
```

## Maintaining

`Formula/gamut.rb` is a copy. The formula is edited in the gamut repository,
as `packaging/gamut.rb`, and `bin/pkgbuild-sha` there copies it here once it
points at a new release; commit and push the copy from here.

Pushing to `main` runs `brew test-bot`'s syntax check. A pull request builds
the formula and its bottles on macOS; to publish the bottles, run the
`brew pr-pull` workflow with the pull request's number, which adds them to
the formula and pushes to `main`.
