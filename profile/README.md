<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="logo-dark.svg">
    <img src="logo.svg" width="280" alt="Yxy">
  </picture>
</p>

<h1 align="center">Yxy</h1>

<p align="center">An open source, compiled, general-purpose systems programming language.</p>

Yxy compiles `.yxy` programs to native executables through LLVM IR and the
system's clang. Integer arithmetic is checked in every build, and a failed
check traps with a stable code and the position of the operation. Every
function declares its effects, and a program reaches the console, files, the
network or the clock only through capabilities that `main` receives.
Ownership and borrows are checked at compile time, with nothing at run time,
and the tools answer in JSON documents whose every key is defined.

Version 0.1.0 is experimental and has not been released yet. Until 1.0 the
language, the standard library and the tools may change, also in ways that
break programs.

The name comes from Tupi-Guarani and means a queue, a line; in some readings
it also means *linear*, which is the intent of the language.

## Start here

```sh
git clone https://github.com/yxy-develop/yxy
cd yxy
cargo build --release
target/release/yxy --version
target/release/yxy run examples/hello.yxy    # Hello, Yxy! / The answer is 42
```

Building needs Rust 1.96 or later, only for the compiler, which has no
third-party crates, and clang, which turns the LLVM IR that `yxy` emits into
executables: Apple clang 21 on macOS, LLVM's clang 20, 21 or 22 on Linux.

- [yxy.dev](https://yxy.dev)
- [Documentation](https://yxy.dev/docs)
- [Language guide](https://yxy.dev/docs/guide) ([guia em português](https://yxy.dev/pt/docs/guia))
- [Standard library](https://yxy.dev/docs/std)
- [Diagnostics, traps and exit statuses](https://yxy.dev/docs/diagnostics)
- [JSON documents](https://yxy.dev/docs/json)
- [Discussions](https://github.com/orgs/yxy-develop/discussions)

## Ecosystem

| Repository | Responsibility |
| --- | --- |
| [yxy](https://github.com/yxy-develop/yxy) | Compiler and toolchain: `check`, `build`, `run`, `fmt`, `test`, `lsp`, `inspect`, `doc`, and the standard library |
| [spec](https://github.com/yxy-develop/spec) | Language specification and language decisions: how Yxy should behave |
| [yxy.dev](https://github.com/yxy-develop/yxy.dev) | Source of the website and of the documentation it renders |
| [homebrew-tap](https://github.com/yxy-develop/homebrew-tap) | Homebrew formula for `yxy`, on macOS and Linux |
| [discussions](https://github.com/yxy-develop/discussions) | Organization-wide Discussions hub |

## Participate

Questions, ideas, language proposals, documentation work, and release
conversations belong in
[Yxy Discussions](https://github.com/orgs/yxy-develop/discussions). Defined
work and defects belong in the affected repository's Issues.

Read the organization-wide
[contribution guide](https://github.com/yxy-develop/.github/blob/HEAD/CONTRIBUTING.md),
[support policy](https://github.com/yxy-develop/.github/blob/HEAD/SUPPORT.md),
[security policy](https://github.com/yxy-develop/.github/blob/HEAD/SECURITY.md),
and [code of conduct](https://github.com/yxy-develop/.github/blob/HEAD/CODE_OF_CONDUCT.md)
before opening a report. For anything else, write to
[hello@yxy.dev](mailto:hello@yxy.dev).

## License

The Yxy repositories are open source under the BSD 3-Clause License,
copyright HYZIS - SERVICOS DIGITAIS LTDA - EPP. Check the repository concerned
for its exact terms.

Yxy is built by HYZIS. The site is made with
[Arandu](https://github.com/arandu-io).
