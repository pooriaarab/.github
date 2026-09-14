# .github

Default community health files for every repository under
[@pooriaarab](https://github.com/pooriaarab).

## What this is

GitHub reads four files from this repository and displays them on any repository
this account owns that does not carry its own copy:

| File | Where it shows up |
|---|---|
| [`CODE_OF_CONDUCT.md`](CODE_OF_CONDUCT.md) | The repository's Community Standards page, and the contributing sidebar. |
| [`CONTRIBUTING.md`](CONTRIBUTING.md) | A banner when someone opens a pull request or an issue. |
| [`SECURITY.md`](SECURITY.md) | The Security tab, and the "Report a vulnerability" flow. |
| [`SUPPORT.md`](SUPPORT.md) | A link on the new-issue page. |

It covers 107 repositories, public and private, from one place.

## Why it works this way

GitHub applies these defaults to a repository "regardless of the destination
repository's visibility", so the 74 private repositories inherit them too. Two
conditions matter and both are easy to get wrong:

- **This repository must be public.** GitHub's rule is that "a repository for
  default files cannot be private". Make it private and nothing inherits, with
  no warning anywhere.
- **A repository's own file always wins.** Copy one of these files into a
  repository and that repository stops tracking this one. For issue templates
  the override is total: any local `.github/ISSUE_TEMPLATE` content makes GitHub
  ignore the defaults entirely rather than merge them.

So a repository should copy a file here only when its content genuinely differs.
A copy that merely repeats the default is a file that goes stale by itself.

## What is deliberately not here

- **No LICENSE.** GitHub cannot default one. A license must sit in the
  repository so it travels with a clone, a package, or a zip. Every repository
  carries its own.
- **No `FUNDING.yml`.** There is nothing to fund yet. An empty sponsor button is
  worse than none.
- **No issue or pull request templates.** Those are generated per repository by
  `issue-standards` and `pr-standards` in
  [pooriaarab/scripts](https://github.com/pooriaarab/scripts), because the
  templates carry a per-repository prefix. One owner per file.

## Verify it is working

Pick any repository and open its community profile:

```bash
gh api repos/pooriaarab/skills/community/profile \
  --jq '.files | {code_of_conduct, contributing, license}'
```

A file that resolves through this repository reports a `url` under
`pooriaarab/.github`. Verified on 2026-09-14, minutes after this repository was
created: `skills` (public) and `offrouter` (private) both resolved their code of
conduct here, and `offrouter` kept its own `CONTRIBUTING.md`, which is the
override working as documented.

One trap. That endpoint does **not** report a security policy, inherited or
otherwise — there is no `security` key in its `files` object. Check the policy
page instead:

```bash
curl -sL https://github.com/pooriaarab/skills/security/policy | grep -c "Report a vulnerability"
```

## The standards these files encode

- [`repo-standards.md`](https://github.com/pooriaarab/scripts/blob/main/repo-standards.md) — the repository and its README.
- [`pr-standards.md`](https://github.com/pooriaarab/scripts/blob/main/pr-standards.md) — the change.
- [`issue-standards.md`](https://github.com/pooriaarab/scripts/blob/main/issue-standards.md) — the request.

## License

The `CODE_OF_CONDUCT.md` here is the [Contributor Covenant](https://www.contributor-covenant.org)
v2.1, used under its own terms. Everything else is MIT. See [LICENSE](LICENSE).
