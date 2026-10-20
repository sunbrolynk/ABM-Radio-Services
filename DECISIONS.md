# Decisions

What I decided for the ABM Radio services, what I turned down, and why. Server specifics (host
names, addresses, paths) live in my private notes, never here.

## A separate repo from the catalog

- **Chosen:** the running services live here, apart from `abm-radio`.
- **Why:** `abm-radio` holds data and stdlib-only scripts, with no secrets and no long-running
  code. Services need containers, real dependencies and secrets in their environment, which is a
  different set of risks and reviews.

## The repo is public

- **Chosen:** public, for the same reason as `abm-radio`: GitHub's free plan only gives branch
  rulesets, secret scanning, push protection and private vulnerability reports to public repos.
- **Rejected:** private. It would mean no enforced pull-request rule on `main` and `dev`.
- **What it costs:** no secret and nothing about my network is ever committed. Secrets live in
  each service's environment; `scripts/check-secrets.sh` and GitHub's push protection catch
  mistakes, and `scripts/check-public.sh` blocks home-network details.
