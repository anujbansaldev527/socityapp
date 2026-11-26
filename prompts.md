# Reusable AI prompts / AI ko baar-baar use karne wale prompts
Use at repository root. Read targeted files, not entire history every time. / Context aur credits bachane ke liye targeted files padhein; actual token saving guaranteed nahi.

## START M01 — first implementation / Pehla coding prompt
```text
Act as senior full-stack engineer. Read AGENTS.md, rules.md, tracker.md, progress.md, documentation.md, ui-ux.md and milestones/M01-foundation.md plus contracts/health.openapi.json. Inspect the repo first. Implement only M01 in task order; do not start M02 or live providers. Bootstrap a reproducible pnpm workspace with Next.js/TypeScript and Expo React Native, portable shared contracts, validated env, MongoDB connector, synthetic seed, local health API and real mobile health client, CI and tests. Use stable compatible versions and commit lockfile. Run acceptance commands; do not claim unexecuted tests. If dependency/network/device access unavailable, mark BLOCK, preserve work, record exact error and next action. Update tracker.md, logs.md and progress.md for each task, then provide concise handoff. No paid services, real customer data, live credentials, external deployments, or unrelated features.
```
Hinglish: Pehle milestone ka complete working foundation banao, existing files check karo, actual test run karo aur blockage record karo; auth, billing aur live deployment abhi nahi.

## Resume / Continue work
```text
Read AGENTS.md, rules.md, tracker.md, progress.md and last 3 logs.md entries. Inspect git status and relevant diffs. Summarize current milestone, next unblocked task, known blockers and acceptance criteria in <=10 lines. Then implement only that task, run relevant checks and update tracking docs. Do not rescan historical docs unless necessary.
```
Hinglish: Last state se continue karo, repeat planning nahi, ek next task complete karo.

## Quick status (read-only) / Current progress
```text
Read tracker.md and progress.md plus last 3 log entries. Compare git status if available. Report done/in progress/todo/hold/block counts, weighted percentage, actual hours, remaining estimate, QA and deployment status, and next task. Do not modify anything or invent data. Keep under 250 words.
```
Hinglish: Short status do, actual record ke basis par, file change nahi.

## Audit / Independent review
```text
Review the current milestone, changed files and rules.md. Prioritize tenant isolation, auth, injection, secret exposure, financial invariants, idempotency, data retention, error handling and integration gaps. Output severity, file/line, evidence, correction and acceptance test. Do not change scope or code until requested.
```
Hinglish: Critical security aur functionality gaps evidence ke saath identify karo.

## QA / Test only
```text
Read current milestone acceptance criteria and latest changed modules. Run relevant tests, typecheck, lint and builds if available. Include negative cases, actual commands, exit codes and defects. For unexecuted checks say NOT RUN. Update QA log and tracker without marking incomplete work DONE.
```
Hinglish: Jo test run nahi hua usko pass mat bolna; failure record karo.

## Enhance existing task / Purana feature improve
```text
Find the completed task and original log. Create a new enhancement ID referencing it; inspect current behavior and tests, preserve backward compatibility, define acceptance, implement and test the smallest change. Append dated enhancement log and recalculate tracker weights without double counting.
```
Hinglish: Done task ko overwrite na karo; naya enhancement record banao.

## Fix blocker / Block resolve
```text
Read blocked task and actual error. Reproduce safely; inspect environment, configuration and dependencies. Propose minimal fix and run regression tests. Do not bypass security or activate paid services. If still blocked, record exact dependency, owner and next action.
```
Hinglish: Root cause fix karo; workaround se security weak nahi karni.

## Session close / Handoff
```text
Update tracker, append logs with ISO timestamps and observed duration, update progress metrics/QA/deploy records, note changed files and commit if authorized. List unresolved blockers and next task. No invented estimates, completion or test results. Keep report short.
```
Hinglish: Session end par actual status save karo taaki agla AI same point se continue kare.

## Deployment review / Release se pehle
```text
Read rules, documentation, release gates and QA results. Verify environment isolation, provider eligibility, secrets, migration compatibility, backup/restore, rollback, store policy and approval. Produce go/no-go with evidence; do not deploy or spend without explicit approval.
```
Hinglish: Release checklist verify karo, permission ke bina deploy nahi.

## Resume v0.3 / Existing source se continue
Read AGENTS.md, tracker.md, latest progress/log and README. Do not scaffold over existing apps. Resolve M01 dependency blocker, generate lockfile, verify Expo compatibility, run all actual acceptance checks. Fix observed issues and update records. Only proceed M02 after approval and acceptance. / Existing code preserve karein, pehle testing complete karein.

