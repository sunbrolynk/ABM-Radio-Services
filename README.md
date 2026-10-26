<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="docs/readme/abm-wordmark-dark.svg">
    <source media="(prefers-color-scheme: light)" srcset="docs/readme/abm-wordmark-light.svg">
    <img src="docs/readme/abm-wordmark-dark.svg" alt="AudioBook Manager" width="560">
  </picture>
</p>

<p align="center"><b>ABM Radio services: the small programs that run alongside the stations.</b></p>

<p align="center">
  <img src="https://img.shields.io/badge/status-setting%20up-orange?style=for-the-badge" alt="Status: setting up">
  <img src="https://img.shields.io/badge/python-3.12-blue?style=for-the-badge" alt="Python 3.12">
  <a href="LICENSE"><img src="https://img.shields.io/badge/license-GPLv3-8b45c6?style=for-the-badge" alt="GPLv3 license"></a>
</p>

<p align="center">
  <a href="https://github.com/sunbrolynk/abm-radio-services/actions/workflows/checks.yml"><img src="https://github.com/sunbrolynk/abm-radio-services/actions/workflows/checks.yml/badge.svg?branch=dev" alt="Checks"></a>
</p>

<hr>

## 📻 What's in here

[ABM Radio](https://github.com/sunbrolynk/abm-radio) is a set of free, openly licensed internet
radio stations: ABM Lofi, Lil' Beats FM and Velvet Static. That repo holds the paperwork: every
track's licence, its proof and the credits. This one holds the programs that run next to the
stations:

| Service | What it does | Status |
|---|---|---|
| Station hosts | The on-air breaks between songs and stories | planned |

Each service gets its own folder, its own container and its own tests when it's built.

## 🔒 Secrets

No key, token or password is ever committed here. Each service reads its secrets from its own
environment. An `.env.example` shows the names it expects, never the values.

## 🛠️ Working on it

- `dev` is the work branch. Branch off it, open a pull request back into it, and I merge `dev`
  into `main`.
- Install the local checks once: `bash scripts/install-hooks.sh`. They scan for secrets, keep
  home-network details out of this public repo, check my writing style, and on push run the
  tests and the changelog check. CI runs the same checks on every pull request.
- Every change to `scripts/` or `src/` needs a changelog entry, normally a `changelog.d/` fragment
  (see [CONTRIBUTING.md](CONTRIBUTING.md)).
- No new dependency without a review, and nothing released less than 14 days ago.

## ⚡ Support the Project

ABM Radio is part of [AudioBook Manager](https://audiobookmanager.com). If you find my work useful,
consider supporting development:

<p align="center">
  <a href="https://ko-fi.com/sunbrolynk">
    <img src="https://img.shields.io/badge/Ko--fi-Support%20Development-FF5E5B?style=for-the-badge&logo=ko-fi&logoColor=white" alt="Ko-fi">
  </a>
  <a href="https://buymeacoffee.com/sunbrolynk">
    <img src="https://img.shields.io/badge/Buy%20Me%20A%20Monster-Support-FFDD00?style=for-the-badge&logo=data:image/svg%2Bxml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCIgZmlsbD0iYmxhY2siPjxwYXRoIGQ9Ik01IDJoMTRsLTEgMThINkw1IDJ6bTIgMmwuNzUgMTRoOC41TDE3IDRIN3oiLz48cGF0aCBkPSJNMTMgNmwtMyA1aDIuNUwxMSAxN2w1LTdoLTNsMi00aC0yeiIvPjxwYXRoIGQ9Ik04IDIwaDh2Mkg4di0yeiIvPjwvc3ZnPg%3D%3D" alt="Buy Me A Monster">
  </a>
</p>

<p align="center">
  <em>Support goes to AudioBook Manager's development. The stations themselves stay free and
  ad-free, and nothing on air is paid for.</em>
</p>

<p align="center">
  Made with ❤️ for audiobook lovers
</p>
