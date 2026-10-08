# Support

## Choose the right channel

- **Usage question:** use [Yxy Discussions][discussions] and choose Q&A / Help.
- **Idea or design proposal:** use Ideas, or RFC / Proposals for a change to the language, the standard library or the tools.
- **Reproducible defect:** open an Issue in the affected repository.
- **Security vulnerability:** use the affected repository's private security advisory. Never open a public Issue or Discussion.
- **Anything else:** write to [contact@yxy.dev](mailto:contact@yxy.dev).

For the compiler, include both lines of `yxy --version` (the version, the host target and the C compiler), the target when it is not the host, the operating system, the smallest `.yxy` program that shows the problem, the exact command and its whole output, and the trap code (`T0001`…), diagnostic code (`E0303`…) or exit status. `yxy check --json` output is useful when a diagnostic is in question.

The Yxy ecosystem uses one organization-wide Discussions hub. Individual repositories do not maintain separate Discussions forums.

Read [the documentation](https://yxy.dev/docs) for the language guide, the standard library, the JSON documents and the diagnostics.

[discussions]: https://github.com/orgs/yxy-develop/discussions
