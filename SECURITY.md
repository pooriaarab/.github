# Security policy

This is the default policy for every repository under
[@pooriaarab](https://github.com/pooriaarab). A repository with a different
policy carries its own `SECURITY.md`, and that copy wins.

## Reporting a vulnerability

**Do not open a public issue.** An issue is visible the moment you file it, and
it stays visible while the fix is being written.

Report it one of these two ways:

1. **Private security advisory.** On the repository, open the **Security** tab
   and choose **Report a vulnerability**. This is the preferred route. It keeps
   the report, the discussion and the fix in one private place, and it is the
   only route that produces a CVE if the issue warrants one.
2. **Direct message** [@pooria_arab on X](https://x.com/pooria_arab), if the
   Security tab is not available on that repository.

Include:

- What the vulnerability is.
- The steps to reproduce it.
- What an attacker gets, in concrete terms.
- A suggested fix, if you have one.

## What to expect

These are side projects maintained by one person. A realistic promise, rather
than a flattering one:

| Stage | Target |
|---|---|
| First reply | Within 7 days. |
| Assessment, with a severity and a plan | Within 14 days. |
| Fix released for a confirmed high-severity issue | Within 30 days. |

If you do not hear back within 14 days, assume the message was missed and send
it again by the other route.

## Disclosure

Please give the fix time to ship before you publish. If you tell me you intend
to disclose on a date, I will work to that date and I will say so if it is not
achievable. I will credit you in the advisory unless you ask me not to.

## Scope

**In scope:** the code in the repository, its released packages, and its default
configuration.

**Out of scope:** findings that need physical access to a maintainer's machine,
social engineering, denial of service by volume alone, automated scanner output
with no demonstrated impact, and vulnerabilities in a third-party dependency
that has already published its own advisory. For a dependency, report it
upstream and open a normal issue here so the version can be bumped.

## Supported versions

Only the latest release of anything published from these repositories is
supported. There are no long-term support branches.

## Secrets

If you find a live credential committed in any of these repositories, report it
by one of the two routes above and treat it as high severity. Do not test what
it unlocks.
