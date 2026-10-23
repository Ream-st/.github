# Contributing to .github

This repository holds [Ream-st](https://github.com/Ream-st)'s GitHub org profile. `profile/README.md` — not the
root `README.md` — is what GitHub actually renders on [github.com/Ream-st](https://github.com/Ream-st); the root
`README.md` is just this repo's own landing page, pointing at that file and listing the org's repos for anyone
who lands here directly. It's [a Stux.Group Service](https://services.stux.group) and isn't open to public pull requests.

## Project conventions

- Keep the projects table in both `README.md` and `profile/README.md` in sync with the actual repos under the
  `Ream-st` org — add a row when a new repo is created, remove one if a repo is archived or deleted.
- Don't duplicate legal or contact content beyond `profile/README.md`'s short summary — the real thing lives at
  [ream.st/legal](https://ream.st/legal).

## Versioning

This project uses [Date Versioning](https://datevers.ing). To release:

1. Add a `## vYY.MM.DD` entry at the top of `CHANGELOG.md`, with its sections in this order: Added, Changed, Fixed, Removed, Security, Deprecated.
2. Set `VERSION.md` to the same bare version (no `v`): today's **UTC** date as `YY.MM.DD`, or `YY.MM.DD-1`, `-2`… for later releases the same UTC day. Never a future date. Use UTC, not local time: just after midnight in the UK it is still the previous day in UTC.
3. Run `bash tests/version.sh`.
4. Run `./commit.sh` (or `commit.bat` on Windows). It checks the version, commits and tags `vYY.MM.DD`, and never pushes.
