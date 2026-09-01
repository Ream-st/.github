# Changelog

All notable changes to Ream-st/.github are documented here.

## v1.1.1

### Fixed
- "Ream-st" (the GitHub org slug) was showing up as display text in the root `README.md` heading and prose — the
  brand name is "Ream.st"; the hyphenated form now only appears inside actual `github.com/Ream-st/...` URLs
- `profile/README.md` was missing a `Repository:` line (root `README.md` already had one, below `Website:`)

## v1.1.0

### Added
- `profile/README.md` — GitHub only renders the org homepage from this exact path, not the repo's root
  `README.md`, so github.com/Ream-st had nothing to show; the root `README.md` is now a smaller landing page
  pointing at it, following the reference pattern used by other Stux.Group orgs

### Fixed
- `commit.bat` echoed an em dash (`—`), which `cmd.exe` garbles into `ÔÇö` under its default (non-UTF-8) console
  codepage — replaced with a plain hyphen in the printed text (the `.sh` equivalents are unaffected, since a
  UTF-8 terminal renders the em dash correctly there)

## v1.0.1

### Fixed
- `README.md` was saved as UTF-16 (a leftover from GitHub's auto-generated placeholder) instead of UTF-8 —
  readable in a GitHub web view but garbled everywhere else (`cat`, most editors, diff tools)

## v1.0.0

### Added
- Org profile `README.md` — project table, legal hub link, and contact addresses
- `CHANGELOG.md`, `VERSION.md`, `CONTRIBUTING.md`
- `commit.sh`/`.bat` — commits and tags a release from the version in `VERSION.md`
