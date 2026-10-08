# Contributing to Yxy

Yxy is a language, its specification, a compiler and toolchain, a website and
a Homebrew tap, each in its own repository. Put each contribution where its
evidence and implementation live:

- Ask usage questions and discuss ideas in [Yxy Discussions][discussions].
- Report a reproducible defect in the affected repository: a wrong result, a
  crash, a confusing message or a gap in the documentation are all welcome.
- Open an RFC in Discussions (RFC / Proposals) before changing the language,
  the public API of the standard library, a JSON document or a diagnostic
  code, before adding a third-party dependency to the compiler, or before
  reversing a recorded decision.
- Report vulnerabilities through the affected repository's private security
  advisory. Never disclose a vulnerability in an issue or discussion.

## Where a change belongs

| Change | Repository |
| --- | --- |
| How the language should behave: syntax, semantics, modules | [spec][spec], through a recorded decision in `decisions/` |
| What the compiler implements: code, tests, the standard library, user documentation | [yxy][yxy], with `docs/implementation/STATUS.md` updated when a requirement changes state |
| The website and the documentation it renders | [yxy.dev][site] |
| The Homebrew formula | [homebrew-tap][tap] |

The specification describes intent and the compiler shows what is
implemented. A divergence between them is recorded in the compiler's
`STATUS.md` and resolved by fixing the code or by a recorded decision in
`spec`, never by editing the specification to match the code.

## Before opening a pull request

1. Link the issue or RFC that defines the work when one exists.
2. Keep the change within one clear scope.
3. Add or update the smallest test that proves the behavior.
4. Run the repository's documented gates.
5. Update public documentation when behavior or an interface changes.

The common gates are:

```sh
# yxy
cargo build --all-targets    # no warning
cargo test

# yxy.dev
export GOWORK=off
aru view:build
gofmt -l $(find . -name '*.go' -not -path '*/testdata/*' -not -name '*.kyse.go')
go build ./... && go vet ./... && go test -race ./...
aru doctor

# homebrew-tap
brew style yxy-develop/tap
brew audit --strict yxy-develop/tap/yxy
brew install --build-from-source yxy-develop/tap/yxy
brew test yxy-develop/tap/yxy
```

Each repository's `CONTRIBUTING.md`, `README.md` and `AGENTS.md` override this
common baseline when they define more specific gates. The compiler's
[contribution guide](https://github.com/yxy-develop/yxy/blob/HEAD/CONTRIBUTING.md)
has its build, its tests and its rules for changes.

## Commits

Write commit messages in English. Use a precise imperative subject that says
what changed, and a body that says why when the diff does not:

```text
End by SIGPIPE when a reader closes the pipe of yxy's output
Document the broken-pipe behaviour: exit status, STATUS, changelog
```

Keep commits small and scoped. Commit messages carry the subject, the body
and the sign-off, nothing else.

## Sign-off

Sign each commit with the Developer Certificate of Origin
([DCO](https://developercertificate.org/)):

```sh
git commit -s
```

The line `Signed-off-by: Your Name <you@example.com>` certifies that you wrote
the change or have the right to submit it under the repository's license. The
DCO requirement is proposed and awaits the maintainers' decision; until it is
recorded in the compiler's contribution guide, follow what the maintainers ask
in the review of your change.

## Definition of Done

A change is complete when all applicable items are true:

- [ ] Implementation is complete.
- [ ] Tests and repository gates pass.
- [ ] A commit exists and its SHA is recorded in the issue or pull request.
- [ ] The public issue is linked and reflects the final state.
- [ ] Documentation is updated when behavior or an interface changed.
- [ ] `STATUS.md` is updated when a requirement of the compiler changed state.
- [ ] A language change has its recorded decision in `spec`.
- [ ] The change is listed in `CHANGELOG.md` when it reaches users.

Historical records follow the stricter evidence rules in the
[Engineering Traceability Policy](docs/ENGINEERING_TRACEABILITY.md).

## Conduct and license

Everyone taking part follows the [Code of Conduct](CODE_OF_CONDUCT.md). By
contributing, you agree that your contribution is licensed under the license
of the repository you contribute to.

[discussions]: https://github.com/orgs/yxy-develop/discussions
[spec]: https://github.com/yxy-develop/spec
[yxy]: https://github.com/yxy-develop/yxy
[site]: https://github.com/yxy-develop/yxy.dev
[tap]: https://github.com/yxy-develop/homebrew-tap
