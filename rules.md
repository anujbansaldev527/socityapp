# Permanent Project Rules / Project ke permanent niyam
Version 0.2. Applies to web, API, mobile, database, infrastructure and AI agents.

| ID | English rule | Hinglish explanation |
|---|---|---|
| R01 | One multi-tenant product, no client-specific forks by default. | Har society ka alag code nahi; same platform mein isolated workspace. |
| R02 | Local-first, synthetic data only until approved pilot. No paid/live services without owner approval. | Testing mein dummy data; paid plan ya real payment bina permission nahi. |
| R03 | Next.js App Router, TypeScript strict, MongoDB, React Native Expo Android first. | Stack same rakhein; iOS aur AWS later. |
| R04 | Modular monolith; domain logic independent of framework and provider adapters. | Business logic route handler mein mix mat karein; migration easy rahe. |
| R05 | REST /api/v1, shared validated DTOs and generated/maintained OpenAPI. Mobile never connects directly to DB. | Web aur app same API use karein; DB direct expose nahi. |
| R06 | Default deny; server verifies authenticated membership, tenant, resource scope and action for every protected operation. | Frontend role ya tenantId par trust nahi; har API par permission check. |
| R07 | Global user identity separate from scoped membership; multiple societies and properties supported. | Ek login, multiple society membership; data mix nahi. |
| R08 | Platform admin sees operational metadata only by default; exceptional support access is time-limited and audited. | Super admin ko unnecessary private data access nahi. |
| R09 | Validate input/output, reject unknown query operators, limit sizes and pagination; prevent NoSQL injection, XSS, CSRF, SSRF and IDOR. | Har input validate karein; user ka raw Mongo filter use nahi. |
| R10 | Web secure HttpOnly cookies + CSRF; mobile short-lived access tokens and rotated refresh tokens in secure storage. | Web token JS mein nahi; mobile secrets SecureStore mein. |
| R11 | MFA for privileged production accounts; throttle login/OTP and revoke compromised sessions. | Admin account extra secure rakhein. |
| R12 | Secrets in environment/secret manager only; redact logs; no real secrets in Git, prompts, client bundles or screenshots. | API key aur password kabhi commit ya share nahi. |
| R13 | Database references checked within tenant; tenant-aware indexes and versioned migrations. | MongoDB foreign keys enforce nahi karta; service layer verify kare. |
| R14 | Money in integer paise with safe bounds; balanced double-entry ledger; immutable posted entries; reversals and transactional allocation. | Float se accounting nahi; posted entry delete/edit nahi, reversal karein. |
| R15 | SaaS billing separate from society maintenance; provider-signed webhooks, replay protection, idempotency and reconciliation. | Apni subscription aur society ke funds alag; screenshot payment proof nahi. |
| R16 | Durable jobs use leases, retries, backoff, deduplication and dead-letter handling; no in-memory production job queue. | Job repeat ho to duplicate bill ya notice nahi banna chahiye. |
| R17 | Private storage, upload allowlists, size limits, signed URLs and malware checks before real use. | Documents public URL par expose nahi; upload verify karein. |
| R18 | Data minimisation, role-scoped notifications, retention, deletion/export and legal holds. | Unnecessary Aadhaar/biometric/visitor data collect nahi. |
| R19 | Production backup encryption, restore drills and recovery objectives before launch. | Backup sirf banana nahi; restore bhi test karein. |
| R20 | Responsive, keyboard-accessible, bilingual English/Hindi UI; follow ui-ux.md. | Senior citizens aur guards ke liye simple interface; Hinglish docs alag. |
| R21 | No fake buttons, static success, invented results, hidden incomplete paths or placeholder production credentials. | Jo functionality ready nahi usko clearly disabled/label karein. |
| R22 | Every change includes relevant tests; no DONE without acceptance evidence. | Test execute kiye bina pass claim nahi. |
| R23 | Separate local/test/staging/prod; destructive commands require explicit approval; production data never copied to dev. | Environment mix nahi; delete/reset se pehle permission. |
| R24 | Version locks, reproducible install, CI, dependency/security scans; review upgrades deliberately. | Latest package blindly install nahi; lockfile commit karein. |
| R25 | Update tracker/logs/progress/contracts/ADRs in same change; preserve history. | Har task ke saath documentation update. |
| R26 | No commercial use of ineligible free plans; check current provider terms and quotas before hosting. | Free hosting rules check karein; local fallback rakhein. |
| R27 | No live subscription or recurring mandate until legal, payment, cancellation, refund and privacy gates approved. | Real billing activate karne se pehle compliance aur owner approval. |
| R28 | Android companion app first; verify store billing and privacy policies before adding purchase links. | Play Store policy ke hisaab se app flow rakhein. |
| R29 | Prefer simple measurable solutions; scale based on latency, DB load, job backlog and cost. | User count dekhkar blindly AWS shift nahi. |
| R30 | Society operations handled by its committee; platform support handles technical exceptions. | Water/lift complaint founder ko assign nahi hogi. |
| R31 | Record all estimates as estimates; dates and effort only from observed evidence. | Fake hours, days ya percentage nahi. |
| R32 | Do not claim fully autonomous operation; security/payment disputes require human escalation. | Automation ke baad bhi critical issues human review mein jayenge. |

## Change control / Rule change
Record ADR ID, reason, alternatives, approval, date and migration impact. No agent may silently relax security, pricing, scope, or spending controls. / Rule change ka proper approval aur record zaroori hai.
