# Security Policy

## Reporting a vulnerability

Do not disclose a suspected vulnerability in an issue, pull request, or
Discussion.

Open the affected repository, select **Security**, then **Report a
vulnerability**. The report creates a private security advisory visible only to
the reporter and repository maintainers. If you cannot use GitHub's private
reporting, write to [contact@yxy.dev](mailto:contact@yxy.dev) without the
details of the vulnerability, and a maintainer will arrange a private channel.

Include what you can of:

- the affected repository and version; for the compiler, both lines of
  `yxy --version` and the host;
- the smallest program or input that shows the problem, and the exact command
  that runs it;
- the impact, what happens, and what you expected;
- any proposed fix.

Avoid accessing data that does not belong to you and stop testing when further
work could harm another user or service.

What counts as a vulnerability of the compiler and of the programs it builds
is listed in the compiler's
[security policy](https://github.com/yxy-develop/yxy/blob/HEAD/SECURITY.md).

## Supported versions

Yxy is experimental before 1.0, and its first public release, 0.1.0, has not
been made yet. Until it is, fixes land on the default branch of the affected
repository. From then on, the latest published release of each maintained
repository receives security fixes. A report against an older release is
still useful, but the fix may be released only from the current supported
line.

Maintainers will acknowledge a complete report, assess severity, coordinate a
fix and disclosure, announce the fix in the advisory and in the repository's
`CHANGELOG.md` when it has one, and credit the reporter when requested and
safe.
