# AI agent entry point / Agent ke liye entry point
Read `rules.md`, `tracker.md`, `progress.md` and the current milestone before editing. Read only relevant sections of historical docs; use search instead of repeatedly ingesting all files. / Har baar poora ZIP scan na karein; relevant files hi padhein.
- Pick one unblocked task ID; mark IN_PROGRESS and append start time. / Ek task uthayein aur start record karein.
- Inspect existing code before modifying it; never discard uncommitted user changes. / Pehle existing code samjhein.
- Implement working functionality and tests, run commands, record exact evidence and failures. / Dummy success ya fake tests nahi.
- Update tracker, logs, progress and impacted contracts/docs together. / Code ke saath documentation sync rakhein.
- Never expose credentials, use live payments, deploy externally, or enable paid services without explicit authorisation. / Secrets share nahi karne aur paid deployment bina approval nahi.
- If blocked, record blocker, safe workaround, owner and next action. / Block ko hide na karein.
- Final report: files changed, tests executed, failures, remaining risks, next task. / Session handoff short aur evidence-based rakhein.
