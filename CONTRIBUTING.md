# Contributing

Thank you for looking. This file is the default for every repository under
[@pooriaarab](https://github.com/pooriaarab). A repository that needs different
rules carries its own `CONTRIBUTING.md`, and that copy wins.

Most of these repositories are built and maintained by one person working with
coding agents. The rules below exist because that mix produces more pull
requests than anyone can read carefully. They are not ceremony.

## Before you write code

**Open an issue first.** No issue, no branch. The issue number ties the branch,
the pull request, and the merged commit to one agreed piece of work.

An issue states four things:

- **Job to be done** — what you cannot do today, in your own words.
- **Today / Wanted** — what it does now, and what it must do instead.
- **Acceptance criteria** — each one independently true or false. "Better" is
  not a criterion.
- **How to verify** — steps, then the expected result.

Wait for a reply before you start. An unclear issue does not produce an unclear
pull request. It produces one that closes cleanly against the wrong thing.

## The pull request

**One issue. One PR. One concern. Under 500 lines.**

| Part | Rule |
|---|---|
| Branch | `<prefix>-<issue>-<slug>`, for example `gm-142-fix-onboarding-drop-off`. The prefix is in that repo's `.github/pr-standards.json`. Read it, do not guess it. |
| Title | `[GM-142] Fix onboarding drop-off`. Imperative mood, 10-50 characters, no trailing period, no emoji. |
| Body | `Closes #142`, then `## What`, `## Why`, and `## How I verified`. |
| Size | 500 counted lines and 40 counted files. Lockfiles, build output, snapshots and generated code do not count. |

There is no label that clears the size cap. If a change does not fit, it is more
than one change. Split it.

**Show your work.** `## How I verified` carries a command and its real output,
or a before-and-after screenshot for anything a person can see. "Tested locally"
proves nothing. A picture proves something.

**Run the checks before you push.** Prefer `bun run ci:local` or
`npm run ci:local`. If neither exists, run the same lint, typecheck and test
commands that CI runs. Do not use CI as your test runner.

## Writing style

Documentation, README text and release notes follow the
[Google developer documentation style guide](https://developers.google.com/style).
Short sentences. Active voice. Present tense. One instruction per sentence.

A repository's README follows the repo standard: one sentence saying what it is,
one command to run it, one screen to decide from, and nothing in it that is not
true.

## If an agent wrote it

Say so. Every pull request body ends with:

    Assisted-by: <agent>:<model>

for example `Assisted-by: claude-personal-2:claude-opus-5`. This is not a
`Co-authored-by` trailer and it does not go in the commit message. It exists so
that months later it is possible to tell which tool produced which class of
defect. Commit messages themselves carry no model attribution at all.

## Commit messages

[The seven rules](https://cbea.ms/git-commit/). Imperative subject, 50
characters or fewer, no trailing period. Blank line. Body wrapped at 72 columns
explaining what changed and why. A repository's own rules win over these.

## No backward compatibility

When you replace something, delete what it replaced, in the same pull request.
No shims, no aliases for a renamed flag, no deprecation period, no `legacy` or
`_old` names left behind. One way to do one thing.

A kept path doubles the state the next contributor has to reason about, and the
old path gets copied as often as the new one.

## What happens next

The owner reviews and merges. Automated review runs on most repositories and
may push fixes straight to your branch, so pull before you push again.

Be patient. These are side projects.
