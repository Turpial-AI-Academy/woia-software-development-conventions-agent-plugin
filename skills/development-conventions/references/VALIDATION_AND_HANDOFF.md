# Validation and Handoff

## Operational completeness gate

The convention artifact is complete only when another contributor can answer these questions from repository-owned evidence without guessing:

1. How do I bootstrap and run the normal development workflow?
2. Which exact checks do I run before calling work complete?
3. Which source/module/API/generated/configuration boundaries must I preserve?
4. What naming/code conventions are mechanically or explicitly required?
5. What is the Git/branch/PR/merge/tag policy?
6. Which changes require tests, docs, migration, security, or other specialized evidence?
7. What exceptions, conflicts, platform caveats, or unresolved owner decisions exist?

For ASPS `development-conventions/v1`, this is the practical meaning of the gate that another agent can work and validate without guessing commands, boundaries, Git policy, or quality criteria.

## Command validation

For each canonical command:

- verify the command is declared by the repository or its documented external system;
- verify the working directory/scope when non-obvious;
- verify required bootstrap/preconditions;
- execute it when the current task requires proof and execution is authorized;
- record blocked commands separately.

A command that merely looks conventional is not evidence.

## Boundary validation

Cross-check the artifact against current architecture/technical-design evidence and representative implementation.

Confirm that:

- ownership/dependency direction is not invented;
- public/internal boundaries are named correctly;
- generated/vendored files are treated correctly;
- exceptions are scoped;
- convention text does not silently redesign architecture.

## Git-policy validation

Verify what can be verified from Git/repository-host evidence:

- default/base branch;
- allowed merge modes;
- branch protection/rulesets when accessible;
- tag/release rules;
- PR/review requirements;
- housekeeping expectations.

If host enforcement cannot be inspected, distinguish documented policy from verified enforcement.

## Quality validation

Build a table or list that distinguishes:

~~~text
required
conditional
informational
blocked/unavailable
~~~

Every PASS must name current evidence.

Do not reuse old CI output, another branch's results, or a previous HEAD when the relevant surface changed.

For a bounded amendment, retain durable evidence of actual execution for unaffected surfaces only after establishing unchanged inputs, scope, environment, and obligations. Record why it remains valid. Re-execute only materially invalidated evidence plus mandatory cross-cutting checks; perform fresh observation for mutable runtime or remote-policy facts when required. Label reused evidence separately from current-invocation execution. Assumptions and prior prose claims do not prove a check ran.

## Diff review

Before handoff:

- inspect the final convention artifact for duplicated or contradictory rules;
- remove speculative policy;
- ensure exact commands are copyable;
- ensure links/paths resolve;
- ensure owner decisions are not disguised as discoveries;
- ensure proposals remain clearly labeled;
- ensure no secret values or private host paths were captured.

## Recommended report structure

~~~text
artifact:
scope:
evidence inspected:
preserved conventions:
new/changed conventions:
canonical commands:
development boundaries:
Git/integration policy:
quality criteria:
validation executed:
blocked/skipped validation:
conflicts/unresolved decisions:
exceptions/platform notes:
remaining risks:
~~~

## ASPS integration

ASPS is optional. When this capability is invoked for the ASPS phase-8 contract, use `docs/project/08-DEVELOPMENT-CONVENTIONS.md` unless the orchestrator supplies an equivalent project-owned target.

The portable skill does not require ASPS at runtime.
