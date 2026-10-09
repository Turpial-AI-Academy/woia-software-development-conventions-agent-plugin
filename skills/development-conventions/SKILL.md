---
name: development-conventions
description: Discovers, establishes, and validates repository-specific development conventions. Use when defining or reconciling coding, naming, change, Git, testing, documentation, quality, and agent working rules without imposing arbitrary style preferences.
license: MIT
compatibility: Works across languages, repositories, operating systems, and delivery models; validation uses the target repository's actual tools and governance.
metadata:
  author: Turpial AI Academy
  version: "0.5.7"
---

# development-conventions

## Operating flow

~~~text
DISCOVER -> DECIDE -> IMPLEMENT -> VALIDATE -> REPORT
~~~

## Purpose

Create an evidence-backed development working contract so a human or agent can contribute without guessing commands, boundaries, Git policy, or quality criteria.

This capability is a conventions capability, not a generic style rewrite. Preserve healthy repository-specific choices and make ambiguity explicit.

## Non-negotiable rules

- Discover before prescribing.
- Treat executable repository configuration and current governance as stronger evidence than personal preference.
- Preserve healthy existing conventions unless evidence shows a concrete problem or the owner authorizes a change.
- Do not invent commands, branch protections, quality gates, naming rules, or architectural boundaries.
- Do not turn one repository's language, formatter, package manager, TDD practice, branching model, or commit style into universal policy.
- Separate verified conventions, proposed conventions, conflicts, and unresolved decisions.
- Record exact commands and their source when a command is part of the working contract.
- Never report a skipped, historical, or unexecuted quality check as current PASS evidence.
- Keep security, testing, architecture, CI/CD, and environment policy within their own capability boundaries; reference their established contracts rather than silently taking ownership of them.
- The plugin must remain usable without ASPS.

## Bounded amendment

Use this path when an authoritative convention artifact is healthy, the requested change is local and understood, and the established toolchain, governance, and development boundaries remain unchanged.

1. Locate the existing artifact and its durable evidence; identify the affected section and authoritative configuration.
2. Read current scoped instructions and only the commands, ownership, or policy sources needed to verify that section.
3. Amend the smallest coherent rule or section. Preserve unrelated conventions and still-valid evidence; do not replay the full template or rediscover unrelated implementation patterns.
4. Verify the affected convention plus mandatory invariants: command resolution, development boundaries, effective Git policy, quality criteria, and absence of invented or conflicting rules.
5. Report the amendment, reused evidence, invalidated evidence, checks actually revalidated, and remaining uncertainty.

Load a detailed reference only for an affected decision, unresolved contradiction, or validation obligation. A new turn alone does not require rebuilding a healthy evidence map.

## Deep path

Use the full discovery/decision/validation procedure below for a new artifact, unclear scope, contradictions, unhealthy or unfamiliar conventions, missing durable gate evidence, or a failed invariant. Also expand context for toolchain/runtime/version/platform changes or environment drift, public API/event/schema rules, persisted data or migrations, auth/secrets/security boundaries, deployment/rollback risk, or cross-provider dependency changes. Resolve those risks before reusing evidence.

## Evidence lifecycle

- Reuse only durable, inspectable evidence whose scope, authoritative inputs, environment, and validation obligations are demonstrably unchanged.
- Mark evidence invalidated when the amendment changes a command, boundary, policy, quality requirement, or input it covered; rerun the affected checks and required cross-cutting invariants.
- Freshly execute or observe evidence when required by the current gate or when validity cannot be established. An unchanged document does not prove that external Git governance or the runtime is unchanged.
- Assumptions, inference, recollection, and unexecuted proposals are not validation evidence. Keep reused execution distinct from checks executed in this invocation.

## Discover

For the deep path, read [DEVELOPMENT_CONVENTIONS_STANDARD.md](references/DEVELOPMENT_CONVENTIONS_STANDARD.md) and [DISCOVERY_AND_DECISION.md](references/DISCOVERY_AND_DECISION.md). For a bounded amendment, load only the affected guidance when needed.

Inspect the project surfaces that actually express development policy, as applicable:

- root and scoped agent/contributor instructions;
- README, CONTRIBUTING, engineering standards, ADRs, ownership files, and project documentation;
- package/workspace/build manifests and canonical task runners;
- formatter, linter, compiler/typechecker, code-generation, schema, and documentation configuration;
- source layout, module/package ownership, public contracts, generated/vendored boundaries, and repeated naming patterns;
- tests and test layout;
- CI/release configuration as evidence of required checks;
- Git branch/tag/release practices that are documented or mechanically enforced;
- repository environment declarations and supported platforms.

Build an evidence map before writing rules. Record contradictions instead of silently choosing one source.

## Decide

Use [DISCOVERY_AND_DECISION.md](references/DISCOVERY_AND_DECISION.md).

For each candidate convention:

1. identify the repository surface and evidence;
2. classify it as verified, proposed, conflicting, or unresolved;
3. determine its scope: repository-wide, workspace/package/module-specific, or task-specific;
4. determine whether enforcement is documentary, executable, or external;
5. preserve the current convention when it is coherent and healthy;
6. add or change policy only when needed to remove real ambiguity, satisfy a requirement, or reconcile an explicit conflict;
7. document exceptions and migration notes when the convention cannot be applied uniformly.

For a greenfield repository, establish the minimum useful conventions needed to begin implementation; do not create ceremony for hypothetical future problems.

## Implement

For a new artifact, use the structure in [development-conventions.template.md](assets/development-conventions.template.md). Amend a healthy existing artifact in place without replaying unaffected template sections.

The resulting project convention artifact should make these four questions answerable without inference:

~~~text
What commands do I run?
What boundaries must I preserve?
What is the Git/integration policy?
What evidence means the work is good enough?
~~~

When invoked for ASPS `development-conventions/v1`, write or update:

~~~text
docs/project/08-DEVELOPMENT-CONVENTIONS.md
~~~

For standalone use, place the artifact where the target repository owns durable engineering documentation.

Do not modify unrelated code or tooling merely to make documentation uniform. If implementation changes are authorized to reconcile conventions, keep them minimal and validate the affected surface.

## Validate

Load [VALIDATION_AND_HANDOFF.md](references/VALIDATION_AND_HANDOFF.md) for the validation obligations affected by the amendment; use its complete gate for the deep path.

Validate proportionally:

- verify documented commands exist and resolve to the intended repository tasks;
- verify named configuration/docs paths exist;
- compare documented boundaries and Git policy against current repository evidence;
- run the repository's convention/quality checks when execution is authorized and feasible;
- inspect the final diff for invented or over-broad policy;
- ensure conflicts, exceptions, platform caveats, and blocked checks remain visible.

The core acceptance test is operational: another agent should be able to work and validate without guessing commands, boundaries, Git policy, or quality criteria.

## Report

Report:

1. evidence sources inspected;
2. conventions preserved;
3. conventions added or changed and why;
4. contradictions or unresolved decisions;
5. exact canonical commands;
6. important development boundaries;
7. Git/integration policy;
8. quality criteria and validation actually executed;
9. exceptions/platform notes;
10. artifact path and remaining risks.

Keep observed facts separate from recommendations.

## Detailed references

- [Development Conventions Standard](references/DEVELOPMENT_CONVENTIONS_STANDARD.md)
- [Discovery and Decision](references/DISCOVERY_AND_DECISION.md)
- [Validation and Handoff](references/VALIDATION_AND_HANDOFF.md)
- [Development Conventions Template](assets/development-conventions.template.md)
