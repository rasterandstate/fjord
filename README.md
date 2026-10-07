<p align="center">
  <img src="docs/images/fjord-mark.svg#gh-light-mode-only" alt="Fjord" width="138">
  <img src="docs/images/fjord-mark-dark.svg#gh-dark-mode-only" alt="Fjord" width="112">
</p>

<h1 align="center">Fjord</h1>

<p align="center">
  Native clients for Forgejo and compatible Git forges, including Gitea.<br>
  Connect them to the server and account you already have. Fjord is not a GitHub client.
</p>

<p align="center">
  <a href="https://fjord.sh/?utm_source=github&amp;utm_medium=referral&amp;utm_campaign=fjord-clients">fjord.sh</a> ·
  <a href="https://mobile.fjord.sh/mobile?utm_source=github&amp;utm_medium=referral&amp;utm_campaign=fjord-clients">Fjord Mobile</a> ·
  <a href="https://cli.fjord.sh/cli?utm_source=github&amp;utm_medium=referral&amp;utm_campaign=fjord-clients">fj CLI</a> ·
  <a href="https://docs.fjord.sh/?utm_source=github&amp;utm_medium=referral&amp;utm_campaign=fjord-clients">Docs</a>
</p>

---

## Get Fjord

| Client | Availability | Get it |
| --- | --- | --- |
| **Fjord Mobile** | On the App Store for iPhone and iPad. Free, with an optional one-time Mobile Pro purchase. | [Download on the App Store](https://apps.apple.com/app/apple-store/id6774756338?pt=128751142&ct=gh-readme-01&mt=8) |
| **fj CLI** | Available today for macOS and Linux. Free and open source. | [Install with Homebrew](#fj-cli) |
| **Fjord for Android** | Coming soon. | |

```sh
brew tap rasterstate/tap https://rasterhub.com/rasterstate/homebrew-tap && brew install fj
```

You need a forge to connect to: your own Forgejo server, or one someone runs for you. If you want one, [fjord.sh](https://fjord.sh/?utm_source=github&utm_medium=referral&utm_campaign=fjord-clients) offers managed Forgejo hosting.

## Fjord Mobile

Your self-hosted Git forge on iPhone and iPad. Review pull requests, triage issues, watch your CI, and merge, from anywhere.

<p align="center">
  <a href="https://apps.apple.com/app/apple-store/id6774756338?pt=128751142&amp;ct=gh-readme-01&amp;mt=8"><img src="docs/images/app-store-badge.svg" alt="Download on the App Store" height="48"></a>
</p>

<p align="center">
  <img src="docs/images/fjord-mobile-devices.png" alt="Fjord Mobile reviewing a pull request diff on an iPad with a keyboard, beside the home screen on an iPhone" width="760">
</p>

- **Review pull requests.** Conversation, diffs, changed files, and CI status. Approve, request changes, and merge.
- **Work your issues.** Open pull requests, create and edit issues, comment, label, and assign.
- **Run CI, not just watch it.** Browse Actions runs, read a failed job's log, cancel a run or start one, and download artifacts.
- **Read and fix code.** Browse repositories, commits, branches, and releases. Edit a file and commit it to a branch for a quick fix.
- **Stay current.** A notification inbox, optional push, and Home Screen widgets.

Sign in with a personal access token from your own server. No Fjord account is required, and the token is stored only in the device Keychain. Signing in with a Fjord account adds push notifications and lets you manage multiple accounts and switch between your servers without signing out.

**Free:** connect any Forgejo server, add several servers and accounts, browse, and review, comment on, and merge pull requests. Actions and their logs, push notifications, the contribution widget, reading pull requests offline, and a few offline reviews are free as well.

**Mobile Pro** is a one-time purchase. It adds Needs You (the pull requests waiting on you) on Home and in a widget, multi-line and block comments, offline review beyond the free allowance, Live Activities for runs, advanced notification actions, and the iPad review workstation.

Requires iOS 17 or later. More at [mobile.fjord.sh](https://mobile.fjord.sh/mobile?utm_source=github&utm_medium=referral&utm_campaign=fjord-clients).

## fj CLI

A command-line tool for Forgejo, in the spirit of GitHub's `gh`. Repositories, issues, pull requests, releases, and Actions from one signed, native binary.

```sh
brew tap rasterstate/tap https://rasterhub.com/rasterstate/homebrew-tap && brew install fj
```

Homebrew covers macOS and Linux x86_64. Other install routes are at [cli.fjord.sh](https://cli.fjord.sh/cli?utm_source=github&utm_medium=referral&utm_campaign=fjord-clients).

<p align="center">
  <img src="docs/images/fj-demo.gif" alt="fj viewing a repository and listing issues and pull requests in a terminal" width="760">
</p>

```sh
fj auth login            # authenticate against a Forgejo host
fj repo clone owner/name # clone a repository
fj pr create             # open a pull request from the current branch
fj pr list               # list pull requests for the current repo
fj run watch             # stream the latest Actions run's logs
fj api /user             # make a raw authenticated API request
```

- **Knows where you are.** Inside a clone, fj infers the repository and host from your git remote.
- **Works across hosts.** Sign in to several forges and move between them.
- **Built for scripts.** `--json` on list and view commands, `--json-fields` to pick fields, and `fj api` for everything else.
- **Careful with tokens.** Tokens go to your OS keychain, with a `0600` file fallback on hosts that have none.

fj is open source under the MIT license. Its source and releases are at [rasterhub.com/rasterstate/fj](https://rasterhub.com/rasterstate/fj).

## Works with

| Client | Forges |
| --- | --- |
| Fjord Mobile | Forgejo 7 and newer, and other compatible installations, including Gitea. Actions runs need Forgejo 15; job logs, cancelling a run, and artifacts need Forgejo 16. |
| fj CLI | Built against the Forgejo 7 API and tested on Forgejo 7.0. Newer versions are expected to work, and Gitea 1.21 mostly works. See the [compatibility notes](https://rasterhub.com/rasterstate/fj/src/branch/main/docs/compatibility.md). |

## About this repository

This repository holds product information and public feedback for the Fjord clients. It is not the product source.

- The Fjord Mobile source is not published.
- The fj source and its issue tracker are public at [rasterhub.com/rasterstate/fj](https://rasterhub.com/rasterstate/fj).
- Corrections to the documentation here are welcome as pull requests.

## Feedback

Found a bug or want something added? [Open an issue](https://github.com/rasterandstate/fjord/issues/new/choose) and pick the form for your client.

Issues here are public. Remove access tokens, private server URLs, and private repository names from anything you post.

Fjord Mobile is developed in a private tracker and fj on rasterhub, so here is what the labels on your issue mean:

| Label | Meaning |
| --- | --- |
| `needs-info` | We asked for more detail and are waiting on you. |
| `tracked` | Accepted and being worked on. The issue stays open until the fix is released. |
| `fixed-in-release` | The fix is publicly available. The closing comment names the version. |
| `not-planned` | Closed without a change. The closing comment says why. |

Security problems should be reported privately. See [SECURITY.md](SECURITY.md).

---

<p align="center">
  A <a href="https://rasterstate.com/?utm_source=github&amp;utm_medium=referral&amp;utm_campaign=fjord-clients">Raster &amp; State</a> project. © 2026 Raster &amp; State LLC.
</p>

<p align="center">
  <sub>
    Nothing in this repository grants a license to the Fjord client software or to the Fjord and Raster &amp; State names and marks.<br>
    Fjord is a third-party client. It is not affiliated with, endorsed by, or sponsored by Forgejo, Codeberg, Gitea, or any server operator.
  </sub>
</p>
