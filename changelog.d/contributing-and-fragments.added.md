- **Contributing guide and changelog fragments:** `CONTRIBUTING.md` and issue templates follow the
  catalog repo's, and a change can add one `changelog.d/<slug>.<section>.md` file holding its
  bullet instead of editing `CHANGELOG.md`. `collate-changelog.py` folds them under `[Unreleased]`
  at release time, and `check-changelog.sh` takes a fragment as coverage the same way it takes a
  `CHANGELOG.md` entry.
