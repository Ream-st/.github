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

## Branches and going live

- **`main` is what's live.** Nothing is pushed to it directly: it only changes when a pull request from `staging` is merged. GitHub shows the org profile from `main`.
- **`staging` is the last check before live.** It only changes when a pull request from `test` is merged.
- **Work happens on `test`**, or on a feature branch off `test` that's merged back into it. Releases are made on `test` too; `commit.sh` / `commit.bat` refuse to run on `staging` or `main`.
- **Going live:** push `test` with its tag, open a pull request into staging (`gh pr create --base staging --head test`), check staging once it's merged, then open one from staging into main (`gh pr create --base main --head staging`). Leo reviews and merges both, with merge commits, so the release tags made on `test` stay in `staging`'s and `main`'s history.

## Versioning

This project uses [Date Versioning](https://datevers.ing). To release:

1. Add a `## vYY.MM.DD` entry at the top of `CHANGELOG.md`, with its sections in this order: Added, Changed, Fixed, Removed, Security, Deprecated.
2. Set `VERSION.md` to the same bare version (no `v`): today's **UTC** date as `YY.MM.DD`, or `YY.MM.DD-1`, `-2`… for later releases the same UTC day. Never a future date. Use UTC, not local time: just after midnight in the UK it is still the previous day in UTC.
3. Run `bash tests/version.sh`.
4. Run `./commit.sh` (or `commit.bat` on Windows). It checks the version, commits and tags `vYY.MM.DD`, and never pushes. It refuses to run on `main` or `staging`.
   Then push with `git push origin test --tags` and open a pull request from `test` into `staging`;
   once that's merged and checked, open one from `staging` into `main` (see [Branches and going live](#branches-and-going-live)).
