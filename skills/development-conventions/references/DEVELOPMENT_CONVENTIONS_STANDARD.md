# Development Conventions Standard

## Objective

A development convention is useful when it removes a recurring implementation decision, prevents a known class of inconsistency, or makes a repository boundary explicit.

The goal is an **operative working contract**, not maximum policy density.

## Evidence hierarchy

Prefer stronger, current evidence over weaker inference. A typical authority order is:

1. explicit repository/organization governance and owner instructions;
2. mechanically enforced repository configuration;
3. canonical executable tasks and CI/release checks;
4. current architecture/technical-design contracts and ownership boundaries;
5. maintained engineering documentation and ADRs;
6. repeated current implementation/test patterns;
7. inference or preference.

This order is not absolute. A scoped instruction may legitimately override a repository-wide default, and an implementation may have drifted from a newer documented decision. Record the conflict and resolve it deliberately.

## Convention record

For every material rule, capture enough context to avoid cargo-culting:

~~~text
area:
rule:
scope:
status: verified | proposed | conflict | unresolved
evidence:
enforcement: documentary | executable | external | none
exceptions:
rationale:
~~~

Do not label a proposal as an established convention.

## Required operational surfaces

A complete convention artifact must cover the following when applicable. If a surface is intentionally absent, say so rather than leaving ambiguity.

### 1. Canonical commands

Document exact project-owned commands for the work developers actually perform, such as:

- bootstrap/install;
- development/start;
- build/code generation;
- format/lint;
- typecheck/compile;
- unit/integration/contract/E2E tests;
- documentation checks;
- package/release validation.

For each important command, record its source and relevant preconditions. Do not invent aliases merely to make different repositories look alike.

### 2. Development boundaries

Make repository boundaries explicit where they affect implementation:

- module/package/service ownership;
- allowed and forbidden dependency directions;
- public versus internal contracts;
- generated or vendored code ownership;
- configuration and secret boundaries;
- persistence/schema/migration ownership;
- platform-specific code;
- files or directories that require special review or must not be edited manually.

Architecture and technical design remain authoritative for architecture decisions. This capability translates those decisions into day-to-day development constraints.

### 3. Language, code, naming, and file conventions

Document only evidenced or deliberately chosen conventions, for example:

- language/compiler strictness;
- formatting/linting ownership;
- identifier/file/directory naming;
- public payload/environment-variable naming;
- import/export rules;
- comments/docstrings;
- error handling and result contracts;
- dependency-introduction policy;
- generated-code rules.

A formatter or linter configuration is stronger evidence than an aesthetic preference.

### 4. Change workflow

Record the minimum expected flow for a material change when the repository defines one:

~~~text
context/spec
-> tests or other executable acceptance evidence
-> implementation
-> focused refactor
-> docs/contracts
-> validation
~~~

Do not make SDD, TDD, trunk-based development, GitFlow, conventional commits, or any equivalent method mandatory unless repository evidence or explicit owner policy requires it.

Bug fixes should preserve a regression when that is a repository quality requirement or is necessary to prevent recurrence.

### 5. Git and integration policy

Document the repository's actual policy for:

- base/default branch;
- feature-branch expectations and naming;
- commit expectations;
- pull request/draft/review requirements;
- merge/rebase/squash policy;
- force-push restrictions;
- required clean-tree or exact-candidate rules;
- tags/releases and tag immutability;
- human authorization boundaries;
- branch cleanup/housekeeping.

Do not infer server-side branch protection from habit; verify it or mark it unknown.

### 6. Quality criteria

Define what evidence is required before a change can be called complete.

Use exact repository checks and distinguish:

- required checks;
- conditional checks;
- informational checks;
- blocked/unavailable checks.

For each required check, record the canonical command or external check name and what it proves.

Never convert "not run" into PASS.

### 7. Testing, documentation, and cross-cutting expectations

Summarize repository-level expectations that developers need during implementation, while preserving ownership of specialized policies.

Examples:

- what types of changes require tests;
- documentation surfaces that must stay aligned with contracts;
- security/privacy review triggers;
- observability or migration evidence required for specific changes.

Reference established specialized policy rather than duplicating it.

### 8. Agent working contract

When agents contribute to the repository, document operational constraints that prevent accidental drift, such as:

- read repository instructions before editing;
- discover the canonical command instead of guessing;
- preserve scoped ownership rules;
- avoid host-global configuration workarounds;
- keep secrets out of prompts/logs/commits;
- inspect final diff and repository status;
- report only current executed validation as PASS.

## Existing repositories

Use preserve-first behavior.

Do not rewrite conventions just because another convention is more fashionable. Change an existing rule only when there is evidence of contradiction, recurring failure, requirement mismatch, or explicit owner intent.

## Greenfield repositories

Choose the minimum sufficient set needed to start safe implementation:

- canonical commands/tooling ownership;
- basic source/test organization;
- public naming/contract conventions where needed;
- dependency/boundary rules inherited from architecture;
- Git/integration policy;
- initial quality gate;
- documentation ownership.

Add further rules only when the project creates the need.

## Anti-patterns

Avoid:

- copying a language/style guide unrelated to the repository;
- documenting commands that were never verified;
- duplicating formatter/linter rules in prose;
- making every observed pattern mandatory;
- silently resolving conflicting instructions;
- mixing architecture redesign into convention work;
- inventing branch protection or review policy;
- declaring every possible quality check required;
- encoding the plugin author's private workspace as project policy.
