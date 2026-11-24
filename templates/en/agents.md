# AGENTS.md — [Project name]

<!-- Starter template: replace placeholders, mark unknowns as open and review together before use. Save as AGENTS.md in the repository root. -->

## Product Context
- Purpose, users and intended improvement: [brief description]
- Principles and explicit boundaries: [state them]
- Authoritative requirements / confirmed spec and human owner: [path or link; person]

## Architecture
- Technologies, directories and relevant entry points: [verified facts only]
- Code, design and language conventions: [existing references]
- Interfaces and fixed constraints: [state them]
- Missing information: [open + responsible person; do not invent]

## Agent Rules
- Before making changes, read the confirmed requirement and relevant project files. Use only the context needed for the task.
- Make small, cohesive changes and reuse existing components. Do not add dependencies or extend scope without the agreed decision.
- Allowed actions, budget and stop conditions: [define explicitly]. This file grants no additional rights.
- For low-risk gaps, choose the smallest reversible solution and record assumptions. Clarify critical uncertainties, conflicts or necessary scope changes with [owner] before the affected implementation.
- Do not include credentials, confidential data or invented check results. Do not weaken acceptance criteria on your own.

## Quality Gates
- Definition of Ready: requirement, scope, examples, owner and relevant project context are clear; affected context files are checked and updated where needed.
- Relevant checks and commands: [existing tests, build and other checks with working directory; mark unknown commands as open]. Match review depth to risk.
- Definition of Done: agreed criteria met, affected documentation updated and results supported by evidence. Explicitly name checks not performed and open findings.
- Review and approval: [record the existing workflow and human decision rights]. Automated checks and agent findings support review; they do not replace human decisions. Resolve blocking findings and recheck; resubmit relevant changes after approval.

## Documentation
- Update all affected .md files with the change, e.g. README.md, architecture notes and this AGENTS.md. Briefly explain if no update is needed.
- Keep documentation, code, spec version and existing language versions consistent. Update generated files at their source: [sources and export commands].

## Feedback & Learning
- Observations and evidence may justify better requirements, processes and agent rules.
- Record proposed changes with their reason, scope, owner and checkpoint. Trial uncertain rules within agreed limits; [responsible person] decides whether to adopt them.
- Version accepted rules, use them in the next task and check their benefit; remove obsolete rules. One failure does not establish a law of nature.
