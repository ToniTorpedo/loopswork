# LoopsWork — agent instructions for this repository

## Product Context

LoopsWork is a framework draft for AI-assisted software development. Build delivers small, verifiable changes; Value evaluates their impact; Learning improves working practices and foundations. People keep decisions and accountability. CART 1.0 is illustrative, not evidence of production outcomes. Preserve Small Specs, Small Context and the three distinct loops, with ten Build, six Value and six Learning steps.

## Architecture & Conventions

This public repository contains reusable Markdown materials, not the website application. `templates/de/` and `templates/en/` hold corresponding specs, prompts, a PR template, scorecard, operational work card, experiment card and AGENTS.md starter. `README.md` explains use; `CONTRIBUTING.md` and `.github/` describe contributions. Existing materials are licensed under CC BY 4.0; preserve attribution and licensing.

The separately maintained website at https://loopswork.dev generates these template and prompt exports from its copy sources. Do not infer website technologies from this repository. No local build command, automated test suite, CI pipeline or named merge reviewer is documented here; mark these as unspecified rather than inventing them.

## Agent Rules

- Read the confirmed requirement and relevant materials first. Work in small, cohesive changes, with only the context needed. Keep DE/EN terminology, filenames and links consistent.
- Preserve the distinction between requirements, agent instructions, technical review, domain acceptance and product impact. An agent instruction file supports Build; it adds no loop, role or step.
- For low-risk gaps, choose the smallest reversible option and document the assumption. Clarify critical uncertainty, conflicting requirements, decision rights or necessary scope/budget changes with the responsible human before the dependent action.
- Respect agreed limits. Do not weaken criteria, silently extend scope, invent evidence or add confidential information. These instructions grant no additional merge or publication rights.
- Keep template changes aligned with the website copy source before the next export; if that source is unavailable, explicitly identify the remaining synchronisation work.

## Quality Gates

Definition of Ready: the requirement, relevant current context and affected Markdown files have been checked and updated where needed. Check Markdown, links, usable placeholders and matching DE/EN content. Compare template exports with the website copy source when available; report checks not performed.

Definition of Done: agreed criteria, affected documentation and evidence match the reviewed version. Follow `CONTRIBUTING.md` for small pull requests with a description and validation. Human review and approval are not replaced by automated checks or agent findings. Resolve blocking findings and recheck; relevant changes after approval need renewed review. A specific reviewer assignment remains unspecified.

## Documentation

Update every affected `.md` file with the change, including this `AGENTS.md` when project context or agent rules change. Briefly explain when no update is needed. Keep README, contribution guidance, bilingual templates and website exports aligned.

This file is specific to the LoopsWork text repository. The reusable starters are [German](templates/de/agents.md) and [English](templates/en/agents.md); adapt one to the target project and save it as `AGENTS.md` in that repository's root.

## Feedback & Learning

Learning evidence may improve requirements, processes and agent instructions. Record the reason, scope, owner and checkpoint for a proposed rule; trial uncertain changes within agreed limits. A human decides whether to adopt them. Version accepted changes, check their benefit in later work and remove obsolete rules. Keep product impact evaluation in Value; one observation does not automatically become a global rule.
