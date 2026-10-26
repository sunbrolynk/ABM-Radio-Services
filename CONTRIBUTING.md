# Contributing

## Changes

Work on a branch off `dev` and open a pull request into `dev`; `dev` reaches `main` in a release
pull request. Explain the problem, the change and how you verified it.

Install the hooks once with `bash scripts/install-hooks.sh`, then let them run on every commit and
push:

- **pre-commit:** the secret scan and the public-repo check (no home-network details, no writing
  that isn't mine), on what's staged.
- **commit-msg:** the public-repo check on the message.
- **pre-push:** the secret scan and public-repo check over the whole history, the changelog check
  over the commits being pushed and the tests, on a clean tree.

Every one has to pass; don't push with `--no-verify`. CI runs the same checks again on the pull
request, apart from my local lists of names and wording.

New logic comes with tests in the same pull request. Every commit that changes `scripts/` or `src/`
needs a changelog entry, in it or in a later commit on the branch: a
`changelog.d/<slug>.<section>.md` file (a short name such as the branch name without its `feat/`
prefix; section `added`, `changed`, `fixed`, `removed` or `security`) holding the bullet as it
should read, bold lead phrase first, so parallel pull requests don't conflict in `CHANGELOG.md`. I
fold them in under `Unreleased` at release time with `python3 scripts/collate-changelog.py`
(`--dry-run` to preview). A commit with no effect anyone would notice opts out with a
`Changelog: none` trailer.

## Secrets

No key, token or password is ever committed. Each service reads its secrets from its own
environment, and its `.env.example` names every one it expects, without values.

## Commit messages

Lowercase and imperative, saying what changed against what it replaced, for example
`read the station key from the environment instead of a config file`.

## Dependencies

Unlike the catalog repo's scripts, a service may take real dependencies, but each one goes through the
full procedure: its own pull request, a hash-pinned lock, a release at least 14 days old, and a read
of the upstream release notes and the code diff between the published versions. Passing checks
alone don't make an update safe.
