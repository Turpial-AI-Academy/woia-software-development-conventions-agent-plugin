# Development Conventions

## Scope

- Repository/workspace:
- Applies to:
- Does not apply to:
- Evidence date / HEAD when relevant:

## Principles

List only durable principles that materially guide development decisions.

## Canonical Commands

| Purpose | Command | Scope / working directory | Source | Required? |
|---|---|---|---|---|
| Bootstrap |  |  |  |  |
| Development |  |  |  |  |
| Build / generate |  |  |  |  |
| Format / lint |  |  |  |  |
| Typecheck / compile |  |  |  |  |
| Tests |  |  |  |  |
| Docs / contracts |  |  |  |  |
| Quality / release gate |  |  |  |  |

## Development Boundaries

### Ownership and dependency direction

-

### Public, internal, generated, and vendored surfaces

-

### Configuration, persistence, and secret boundaries

-

## Code, Naming, and File Conventions

Record only verified or explicitly chosen conventions.

- Language/compiler:
- Formatter/linter:
- Identifiers:
- Files/directories:
- Public payloads/contracts:
- Environment/configuration keys:
- Imports/exports:
- Errors/results:
- Dependencies:
- Generated code:
- Comments/documentation:

## Change Workflow

~~~text
<project-specific flow>
~~~

Document requirements for specs, acceptance criteria, tests-first behavior, refactoring, documentation, code generation, or traceability only when they actually apply.

## Testing and Documentation Expectations

- Tests required when:
- Regression required when:
- Contract/integration/security/migration/observability evidence required when:
- Documentation must change when:

## Git and Integration Policy

- Default/base branch:
- Feature branches:
- Branch naming:
- Commit expectations:
- Pull request/draft/review:
- Merge method:
- Force-push policy:
- Exact-candidate/clean-tree requirements:
- Tags/releases:
- Human authorization boundaries:
- Post-merge branch cleanup:

## Quality Criteria

| Check | Classification | Command / external check | What it proves |
|---|---|---|---|
|  | required / conditional / informational |  |  |

A skipped or unavailable check is not PASS.

## Agent Working Contract

- Discover repository instructions before editing.
- Use canonical commands from repository evidence; do not guess aliases.
- Preserve scoped ownership and architecture boundaries.
- Do not use host-global configuration changes as a repository fix unless explicitly authorized.
- Keep secrets and private host state out of commits and durable docs.
- Inspect the final diff and repository status.
- Report only current executed validation as PASS.

Add or remove agent rules to match the repository's actual governance.

## Exceptions and Platform Notes

-

## Conflicts and Unresolved Decisions

| Topic | Conflicting / missing evidence | Current temporary rule | Owner / next decision |
|---|---|---|---|
|  |  |  |  |

## Evidence Sources

-

For amendments, record the affected sections, evidence reused with unchanged inputs, evidence invalidated, and required fresh checks. Preserve unrelated sections; this template need not be replayed for each local change.

## Validation Executed

| Validation | Result | Evidence / notes |
|---|---|---|
|  | PASS / FAIL / BLOCKED / NOT RUN |  |
