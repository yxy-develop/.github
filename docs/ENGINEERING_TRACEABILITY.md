# Yxy Engineering Traceability Policy

Every completed change must be traceable to its source context, repository, and
Git commit.

## Sources and authority

- The specification (`spec`) says how the language should behave, and its
  recorded decisions say why.
- The compiler's code and tests (`yxy`) show what is implemented, and its
  `docs/implementation/STATUS.md` records the state of every requirement,
  with `docs/implementation/TARGETS.md` for each target and its evidence.
- Git commits and repository state are the source of technical truth.
- GitHub Issues, pull requests, Discussions, and releases are the source of
  public project state.

No source replaces another. A note can explain intent but cannot prove that code
shipped. A commit can prove a diff but may not explain why it exists. A rule in
the specification does not prove that the compiler implements it.

When the specification and the compiler diverge, the divergence is recorded in
`STATUS.md` and resolved by fixing the code or by a recorded decision in `spec`,
never by editing the specification to match the code.

## Public claims

READMEs, documentation, release notes, and the website state only what the
compiler repository shows: its `STATUS.md`, its `TARGETS.md`, its tests, and
its measured results. The website keeps each statement of performance or
guarantee with its source in `claims/ledger.json`. A claim without evidence is
not published.

## Current work

Defined work belongs in an Issue in the repository that owns the implementation.
The Issue links its originating Discussion or RFC, relevant pull requests,
commits, documentation, and release. Cross-repository work may use one tracking
Issue with linked implementation Issues.

## Historical records

Historical backfill preserves original Git history. It never rewrites commit
dates or creates evidence retroactively.

Process records in ascending original date. Prefer the date in a corroborated
record. Otherwise use the relevant commit author date. Every completed
historical Issue must include:

- original date;
- repository and classification;
- one or more full commit SHAs;
- the first verified release containing the change, when released;
- an evidence summary based on the diff and current repository state;
- a completed checklist limited to work the evidence proves.

If no commit, pull request, release, or current code proves a claim, do not mark
it completed. Label it `needs-verification` and state what evidence is missing.

## Public language

Public Issues, pull requests, Discussions, labels, release notes, commits,
templates, and documentation use English. The READMEs also carry a section in
Brazilian Portuguese, and the website serves both languages.

## Workflow boundaries

- Discussion belongs to community conversation.
- Issue belongs to defined or historical work.
- Pull request belongs to implementation review.
- Decision in `spec` belongs to a change of the language.
- Release identifies a published version.
- Documentation explains supported use.
