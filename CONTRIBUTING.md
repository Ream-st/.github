# Contributing to .github

This repository holds [Ream-st](https://github.com/Ream-st)'s GitHub org profile. `profile/README.md` — not the
root `README.md` — is what GitHub actually renders on [github.com/Ream-st](https://github.com/Ream-st); the root
`README.md` is just this repo's own landing page, pointing at that file and listing the org's repos for anyone
who lands here directly. It's a [Stux.Group](https://stux.group) project and isn't open to public pull requests.

## Project conventions

- Keep the projects table in both `README.md` and `profile/README.md` in sync with the actual repos under the
  `Ream-st` org — add a row when a new repo is created, remove one if a repo is archived or deleted.
- Don't duplicate legal or contact content beyond `profile/README.md`'s short summary — the real thing lives at
  [ream.st/legal](https://ream.st/legal).

## Versioning and changelog

- The version lives in `VERSION.md` (a bare version string) — bump it on every release
- Every release gets a `CHANGELOG.md` entry using `### Added` / `### Changed` / `### Fixed` subsections — never a
  bare bullet list directly under a version heading
- `commit.sh` (bash) and `commit.bat` (Windows) read `VERSION.md` and create the matching `git tag` — don't
  hand-edit a version or commit message into either script
