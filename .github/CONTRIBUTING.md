# Contributing

This document describes how you can contribute to Soneta Android. Please read it carefully before opening a pull request.

Soneta is an open-source project forked from Telegram's open-source client code. It is a separate application, not affiliated with Telegram FZ-LLC, and connects to users' existing Telegram accounts over the real Telegram network. This repository covers the Android client — Soneta also has separate repositories for its other platforms, which follow the same contribution guidelines.

**Table of Contents**

* [What contributions are accepted](#what-contributions-are-accepted)
* [Build instructions](#build-instructions)
* [Pull upstream changes into your fork regularly](#pull-upstream-changes-into-your-fork-regularly)
* [How to get your pull request accepted](#how-to-get-your-pull-request-accepted)
  * [Keep your pull requests limited to a single issue](#keep-your-pull-requests-limited-to-a-single-issue)
    * [Squash your commits to a single commit](#squash-your-commits-to-a-single-commit)
  * [Don't mix code changes with whitespace cleanup](#dont-mix-code-changes-with-whitespace-cleanup)
  * [Keep your code simple!](#keep-your-code-simple)
  * [Test your changes!](#test-your-changes)
  * [Write a good commit message](#write-a-good-commit-message)
* [License and attribution](#license-and-attribution)

## What contributions are accepted

We appreciate contributions that fix bugs, improve stability, or optimize this repository's source code and documentation. If you're fixing an existing issue with the app's behavior, please push to your fork and [submit a pull request][pr].

Wait for us — maintainers try to review pull requests as quickly as possible. If there are issues with your pull request, we may suggest changes before merging.

We generally **do not merge** pull requests that introduce new features, new user-facing UI elements, or translations, since those decisions are made centrally by the Soneta team according to the project roadmap, which isn't public. If you'd like to propose a feature, open an issue for discussion first rather than submitting code directly.

If you have a translations-related contribution, check with the maintainers for the current translation process, since this may differ per platform repository.

## Build instructions

See this repository's `README.md` for build environment setup and compilation instructions specific to Soneta Android.

## Pull upstream changes into your fork regularly

Soneta Android advances quickly. It's important to pull upstream changes into your fork regularly. Nothing is worse than putting days of work into a pull request only to have it rejected because it has diverged too far from upstream.

To pull in upstream changes:

    git remote add upstream <this-repository-url>
    git fetch upstream master

Check the log before merging, to confirm you actually want the changes:

    git log upstream/master

Then rebase your changes on the latest commits in the `master` branch:

    git rebase upstream/master

After that, force-push your commits:

    git push --force

For more info, see [GitHub's guide to forking a repository][help_fork_repo].

## How to get your pull request accepted

We want to improve this project with your contributions, while keeping a stable experience for the community. Follow these rules and you should succeed without a problem.

### Keep your pull requests limited to a single issue

Pull requests should be as small and atomic as possible. Large, wide-sweeping changes will be **rejected**, with a request to isolate the specific change. For example:

* If you're making spelling corrections in the docs, don't modify other files.
* If you're adding a new function, don't "clean up" unrelated functions in the same PR — that cleanup belongs in its own pull request.

#### Squash your commits to a single commit

To keep the project history clean, aim for one commit per pull request. If you already have multiple commits, squash them:

1. Open a terminal (Git Bash or equivalent).
2. Run `git reset --soft HEAD~{N} && git commit`, replacing `{N}` with the number of commits to squash.
3. Press <kbd>i</kbd> to enter insert mode.
4. Enter the commit message for the new, combined commit.
5. Press <kbd>ESC</kbd> to exit insert mode.
6. Type `:wq` and press <kbd>Enter</kbd> to save (or `:q!` to discard).
7. Run `git push --force` to push the squashed commit.

For example, to squash the last 5 commits: `git reset --soft HEAD~5 && git commit`

### Don't mix code changes with whitespace cleanup

If you change two lines of code and reformat 200 lines of whitespace in the same file, the resulting diff is unreadable and will be **rejected**. Whitespace cleanups belong in their own pull request.

### Keep your code simple!

Please keep your code clean and straightforward. Favor readable names over abbreviations — for example:

* `opacity` instead of `o`
* `placeholder` instead of `ph`
* `myFunctionThatDoesThings()` instead of `mftdt()`

### Test your changes!

Before submitting a pull request, test your changes. Verify Soneta Android still builds and runs correctly, and that your change doesn't introduce crashes or regressions elsewhere.

### Write a good commit message

* Explain *why* you made the change, not just what changed. [More on writing a good commit message.][commit_message]
* If your commit fixes an issue, close it by [adding a keyword and the issue number][closing-issues-via-commit-messages] to your commit message — for example: `Fix #123`.

## License and attribution

This repository (Soneta Android) is a fork of Telegram's open-source client code. Any application you build from this code needs its own `api_id`/`api_hash` from Telegram (see [core.telegram.org][telegram_api]) and must not use the Soneta name or logo without permission. Make sure any redistribution complies with the inherited open-source license included in this repository.

[//]: # (LINKS)
[help_fork_repo]: https://help.github.com/articles/fork-a-repo/
[commit_message]: http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html
[pr]: ../../compare
[closing-issues-via-commit-messages]: https://help.github.com/articles/closing-issues-via-commit-messages/
[telegram_api]: https://core.telegram.org/api/obtaining_api_id
