# Contributing to .github

This repository holds [Ream-st](https://github.com/Ream-st)'s GitHub org profile — its `README.md` is what
renders on [github.com/Ream-st](https://github.com/Ream-st). It's a [Stux.Group](https://stux.group) project and
isn't open to public pull requests.

## Project conventions

- Keep the projects table in `README.md` in sync with the actual repos under the `Ream-st` org — add a row when a
  new repo is created, remove one if a repo is archived or deleted.
- Don't duplicate legal or contact content here — it links out to [ream.st/legal](https://ream.st/legal).

## Versioning and changelog

- The version lives in `VERSION.md` (a bare version string) — bump it on every release
- Every release gets a `CHANGELOG.md` entry using `### Added` / `### Changed` / `### Fixed` subsections — never a
  bare bullet list directly under a version heading
- `commit.sh` (bash) and `commit.bat` (Windows) read `VERSION.md` and create the matching `git tag` — don't
  hand-edit a version or commit message into either script
