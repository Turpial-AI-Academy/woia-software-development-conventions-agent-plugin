# Discovery and Decision

## 1. Establish scope

Identify the repository root, relevant workspace/package/module scope, task scope, current branch/HEAD when Git evidence matters, and the project-owned location for durable conventions.

For existing repositories, remain read-only while discovering unless mutation is explicitly authorized.

### Continuing a healthy artifact

For a local amendment, reuse the authoritative artifact and objective evidence map when their inputs are unchanged. Inspect the affected section, its configuration/policy sources, and applicable scoped instructions. Preserve unaffected rules and evidence rather than repeating the inventory below. Check command resolution, boundaries, Git governance, and quality criteria whenever their validity is material to the amendment.

Use the full inventory for new artifacts, ambiguous scope, contradictions, unfamiliar conventions, toolchain/platform drift, public or persisted contracts, security/deployment boundaries, dependency restructuring, missing durable evidence, or an invariant failure.

## 2. Inventory evidence

Search by concern, not by a single filename.

### Instructions and governance

Look for:

- AGENTS/agent instructions and scoped equivalents;
- README and CONTRIBUTING;
- engineering standards and team guides;
- CODEOWNERS/ownership metadata;
- ADRs and architecture/technical-design documentation;
- security/release/deployment policy relevant to developers.

### Executable conventions

Inspect:

- package/build/workspace manifests;
- task runners and scripts;
- formatter/linter/typechecker/compiler configuration;
- test configuration and test directories;
- code generation/schema tooling;
- docs validators;
- CI/release jobs as evidence of required checks.

### Implementation patterns

Sample representative current code and tests for repeated patterns that are not already mechanically declared. Prefer multiple current examples over one file.

Do not treat generated, vendored, deprecated, migration-only, fixture, or test-only code as repository-wide policy without evidence.

### Git policy

Inspect repository documentation and Git-host configuration available to you. Distinguish:

- verified local repository practice;
- verified server-side enforcement;
- documented but not mechanically enforced policy;
- unknown policy.

## 3. Build a contradiction register

Typical contradictions include:

- docs name a command that no longer exists;
- CI runs a different gate than contributor docs;
- formatter/linter configuration disagrees with prose;
- architecture boundaries differ from current imports;
- two scoped instruction files disagree;
- Git docs describe a merge mode the host no longer permits.

Record:

~~~text
topic:
source A:
source B:
scope:
impact:
resolution owner:
temporary rule:
~~~

Do not silently pick the source you personally prefer.

## 4. Decide authority

Use the evidence hierarchy in [DEVELOPMENT_CONVENTIONS_STANDARD.md](DEVELOPMENT_CONVENTIONS_STANDARD.md), then account for scope and recency.

Decision outcomes:

- `PRESERVE`: healthy current convention; document or keep unchanged.
- `CLARIFY`: convention exists but wording/scope/evidence is ambiguous.
- `ADD`: no adequate convention exists and a real recurring decision needs one.
- `RECONCILE`: authoritative sources conflict and an explicit resolution is available.
- `PROPOSE`: owner/product/architecture decision is still required.
- `DEFER`: useful but unnecessary for current safe development.

A `PROPOSE` or `DEFER` outcome is not an established project rule.

## 5. Keep policy proportional

Before adding a rule, ask:

1. What ambiguity or failure does this rule prevent?
2. Is the behavior already enforced mechanically?
3. Does this rule need prose, or would a link to the executable source be clearer?
4. Is the rule repository-wide or scoped?
5. Who owns exceptions?
6. How will another developer know whether the rule still applies?

Prefer references to canonical executable configuration over duplicated prose.

## 6. Greenfield decision baseline

When no repository evidence exists, derive conventions from known project constraints and current architecture/technical design.

Choose only what implementation needs now. Mark owner-selected choices as decisions, not discoveries.

At minimum, resolve:

- canonical development/quality commands or the tool that will own them;
- source/test placement;
- public contract naming where relevant;
- dependency/boundary rules inherited from architecture;
- Git/integration expectations;
- minimum definition of done.

## 7. Change control

If convention work requires modifying tooling or code:

- state why documentation alone is insufficient;
- change the smallest owned surface;
- keep behavior changes separate from aesthetic cleanup;
- add regression/validation when the convention is mechanically enforceable;
- update the convention artifact and executable source together when they form one contract.
