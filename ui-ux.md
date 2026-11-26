# UI & UX standard / Modern user-friendly design rules
Provisional design system, not final branding. / Ye initial design tokens hain, final brand approval pending.

| Topic | English | Hinglish |
|---|---|---|
| Audience | Owners, tenants, committees, guards, staff and seniors; prioritise clarity over decoration. | Har age aur non-technical user aasani se use kar sake. |
| Visual style | Clean neutral surfaces, restrained shadows, clear hierarchy; no generic gradient clutter. | Minimal professional design; extra gradient/glass effects avoid. |
| Tokens | Primary #1D4ED8, text #0F172A, muted #475569, light bg #F8FAFC, surface #FFFFFF, border #CBD5E1, danger #B91C1C, success #166534. Dark tokens separate; verify contrast. | Colors tokens se aayenge; hardcode nahi; dark mode separately test. |
| Typography | System/Inter-style Latin, Noto Sans Devanagari fallback; web base 16px, mobile 16sp, headings 24–32, scalable. | Hindi text readable, font family consistent, text zoom support. |
| Spacing | 4px base; 8/12/16/24/32/48; consistent max content width and gutters. | Har section ka margin aur gap consistent. |
| Layout | Desktop sidebar + header + main; mobile bottom tabs for resident, role-specific actions for guards. | Web par clear navigation; app mein common actions ek tap mein. |
| Responsive | Test 320, 375, 768, 1024, 1440 widths; Android small screens, landscape, font scaling. | Mobile par overflow, overlap, cut text nahi. |
| Accessibility | Target WCAG 2.2 AA; visible focus, keyboard navigation, labelled controls, contrast 4.5:1 normal text, touch targets preferably 44–48px/dp. | Color-only status nahi; icon ke saath text, screen reader aur keyboard support. |
| Forms | Clear labels, inline validation, preserve values, explicit error and success, accessible focus. | Galat field ka reason batao; input reset mat karo. |
| States | Loading, empty, error, offline, retry, no permission, expired subscription and partial data. | Har screen ka alternate state designed ho, blank page nahi. |
| Tables | Search, filters, sort, pagination, export permission, responsive list fallback. | Data find karna easy; mobile par horizontal clutter avoid. |
| Finance | INR formatting, period, due date, payer, status, receipt and explicit confirmation. | Paid/pending clear; paisa aur date confusion nahi. |
| Privacy | Mask sensitive fields; no visitor details on public/lock-screen notifications. | Personal info sirf authorised user ko. |
| Localisation | UI strings externalised, English/Hindi switch; no concatenated translation fragments. | Hardcoded texts avoid, Hindi layout test. |
| Notifications | Categorised inbox, unread count, preferences, urgent notice distinct from promotional content. | Important notices group messages mein lost nahi. |
| Performance | Skeletons, lazy-load noncritical content, paginated APIs, optimised images, measure low-end Android. | Slow phone aur internet par bhi usable. |
| Motion | Subtle transitions, reduced-motion support; no mandatory animations. | Animation functionality block nahi kare. |

## Screen inventory / Screens
Public: landing, features, pricing, FAQ, login, register, privacy, terms, contact. / Product samajhna aur signup.
Management: overview, setup wizard, communities/buildings/units, members, maintenance, ledger, expenses, complaints, notices, meetings, events, facilities, security, subscriptions, reports, settings, help. / Committee ka kaam ek dashboard se.
Resident mobile: sign in, join/invite, society switch, home, dues, receipts, complaints, inbox, events, visits, facility booking, profile/help. / Resident apna kaam app se kare.
Guard/staff: assigned gate or work, entry/exit, pending approvals, offline status, shift, task updates. / Sirf duty-related access.
Platform admin: tenant metadata, billing metrics, health, incidents, support, feature flags. / Founder ke liye business control panel; private tenant data default nahi.
M01 implements only foundation health view. Other screens must not be presented as functional until APIs exist. / Abhi sab screens build nahi karni.

## UI acceptance / QA
Verify labels/title case, consistent typography and margins, loading/errors, keyboard and screen reader, tap targets, contrast, real actions, mobile screenshots, Hindi strings, no exposed tenant info. / Har release mein UI QA evidence attach karein.

## v0.3 provisional starter theme / Initial theme
Deep teal #174d46, pale neutral #f3f6f5, dark text #172f2d, shared visual direction across web/mobile. Provisional, not final branding. Current UI English only; Hindi localisation remains pending. / Abhi basic theme hai; bilingual product UI later.

