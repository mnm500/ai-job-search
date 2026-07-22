# /outreach - Draft Cold Outreach to a Referral Contact

You are turning `/scrape` Step 4.5's LinkedIn people-search links into an actual outreach
sequence: picking a target from the visible search results the user opens, drafting a
short connection note or message in the candidate's voice, and logging every touch so the
same person is never contacted twice by accident. `/scrape` generates the links; nothing
acts on them until now.

## ⚠️ Personal use only

This drafts messages for the user to send by hand, one person at a time, from links they
open themselves. It never creates or automates a LinkedIn account, never scrapes or
programmatically fetches people-search result pages, never solves a CAPTCHA, never
guesses or permutes email addresses, and never calls a third-party contact-enrichment
API. Volume guardrails in Step 6 exist to keep this at the pace of genuine, individual
outreach — not a campaign.

Follow these steps **in order**.

---

## Step 0: Parse Input

`$ARGUMENTS` may contain:

- Nothing → list high/medium-fit companies from `job_scraper/seen_jobs.json` that have no
  row yet in `outreach_tracker.csv`, and ask which to target
- A company name, e.g. `/outreach acme` → target that company
- A job number from the most recent `/scrape` run, e.g. `/outreach 3` → resolve it against
  that run's result table

---

## Step 1: Load Context

Read, in this order:

1. `outreach_tracker.csv` (create with the header below if missing) — dedupe against it
   before proposing any new target.
2. `job_search_tracker.csv` — if this company already has an open application, the
   message changes (Step 3's variant), and the outreach otherwise risks contradicting
   what was already submitted.
3. `.claude/skills/job-application-assistant/01-candidate-profile.md` — grounds every
   claim the message makes.
4. `.claude/skills/job-application-assistant/03-writing-style.md` — voice: warm but
   direct, no cliches, no em-dashes, first person active voice, demonstrate don't state.
5. `.claude/skills/job-application-assistant/02-behavioral-profile.md` — match register to
   the candidate's natural style, same rule `/apply`'s reviewer applies to cover letters.

`outreach_tracker.csv` header (create if the file doesn't exist yet):
```
date,company,person_name,person_role,channel,touch_number,message_type,job_ref,status,response,next_action_date,notes
```

---

## Step 2: Target Selection

Reuse the exact LinkedIn people-search URL format from `.claude/skills/job-scraper/SKILL.md`
Step 4.5, plus a hiring-manager-title variant:

**A. Hiring manager (priority target)**
```
https://www.linkedin.com/search/results/people/?keywords=<url-encoded "<Company Name> hiring manager">&origin=GLOBAL_SEARCH_HEADER
```

**B. An engineer/peer on the team**
```
https://www.linkedin.com/search/results/people/?keywords=<url-encoded "<Company Name> <role keyword>">&origin=GLOBAL_SEARCH_HEADER
```

**C. Recruiter / talent acquisition**
```
https://www.linkedin.com/search/results/people/?keywords=<url-encoded "<Company Name> recruiter">&origin=GLOBAL_SEARCH_HEADER
```

**Priority order: hiring manager → an engineer on the team → recruiter/TA → the
company's own LinkedIn page.** Present the links; the user opens and browses them. Read
only what is visibly on the page once they navigate there — **never fetch or scrape
LinkedIn people-search result pages programmatically**, same rule `job-scraper/SKILL.md`
Step 4.5 and Rule 7 already set. Never fabricate a contact or claim a specific person was
found; these are search links, not results.

**Cold-email variant:** only when a public email address exists on the company's own
website (a listed "careers@" or named contact on their team/contact page) — never guessed,
never permuted, never sourced from a third-party enrichment tool.

---

## Step 3: Draft the Touch

Every message is grounded only in facts from the profile files read in Step 1 — same
no-fabrication rule `/apply` and `/outcome`'s follow-up branch already follow.

**T1 — Connection note.** ≤300 characters (LinkedIn's hard limit on connection-request
notes). One specific, genuine reason for reaching out (the role, a shared interest, a
piece of their work). No pitch, no CV attached, no ask beyond connecting.

**T2 — On acceptance, +1 day.** ≤120 words. One low-cost ask (a quick question about the
role or team, not "can we hop on a call"). Reference T1 naturally rather than
re-introducing yourself.

**T3 — +7 days after T2 if silent, once.** Polite close-out — thank them for their time,
leave the door open, no pressure. **Never a fourth touch to the same person.**

**Application-already-in variant:** if Step 1 found an open `job_search_tracker.csv` row
for this company, adjust every touch to reference the application directly ("I recently
applied for <role>...") and ask for a look rather than re-pitching the candidate from
scratch — the application already carries that weight.

Draft only the touch that's actually due (T1 for a new target; T2/T3 only once the prior
touch's outcome is known — see Step 6's cadence rule).

---

## Step 4: Approval Gate

Present the drafted message with its target (name/role if known from the visible page,
channel, touch number) and **wait for approval before doing anything else with it.** On
approval, navigating to the profile and pre-filling the message box is fine; **the Send /
Connect click is always the user's**, never this command's. If the user wants edits,
revise and re-present — don't send an edited version without a fresh approval.

---

## Step 5: Log the Touch

Once the user confirms they sent it (or declines to), append one row to
`outreach_tracker.csv`:

```
date,company,person_name,person_role,channel,touch_number,message_type,job_ref,status,response,next_action_date,notes
```

- `status`: `sent`, `declined` (user chose not to send), `accepted` (connection accepted,
  awaiting T2), `responded`, or `closed` (see Step 6).
- `next_action_date`: when the next touch would become due (T1 sent → recheck after
  acceptance; T2 sent → +7 days for a possible T3).
- Never restructure the CSV or touch other rows — same convention `/outcome` follows for
  `job_search_tracker.csv`.

If the user declined to send, log nothing beyond noting the decline if they want a
record — do not silently drop it either way; ask.

---

## Step 6: Volume Guardrails

Enforce these before drafting a new **first** touch (T2/T3 to someone already in
sequence don't count against the daily/weekly caps — they're continuations, not new
outreach):

- **≤5 new people per day, ≤15 per week.** Count `sent` rows in `outreach_tracker.csv`
  with today's date / within the last 7 days. If a cap is hit, say so and stop — don't
  draft more until the window resets.
- **≤2 people per company.** Check existing rows for the target company before adding a
  third.
- **No identical message text across people.** Each draft must be written fresh from
  Step 3's grounding, even when the shape is similar.
- **Two silent touches (T1 accepted + T2, or T1 alone if never accepted) end the
  sequence** — mark `closed` after T3 with no reply, or after T1 sits unaccepted for 14+
  days. **No re-contact of the same person for 6 months** after `closed`.

---

## Step 7: Confirm

Summarize what happened this run: who was contacted (or drafted-but-declined), which
touch number, and the tracker row written. If any application in `job_search_tracker.csv`
is still open and 10+ days quiet, mention that `/outcome followup` covers the application
side of chasing a quiet company — outreach and application follow-up are deliberately
separate flows that both feed the same tracker.

---

## Important Rules

1. **Never send.** Every message is drafted and approved for the user to send by hand;
   the Send/Connect click is never this command's.
2. **No ToS circumvention.** No CAPTCHA solving, no anti-bot evasion, no bulk automation,
   no fake or duplicate accounts, no email-guessing or permutation tools, no third-party
   enrichment APIs.
3. **No automated people lookups.** LinkedIn people-search results are links the user
   opens and browses themselves — never fetched or scraped programmatically.
4. **No fabricated contacts.** Never claim a specific person was found by this command;
   the user finds them by browsing the search link.
5. **No fabricated claims in messages.** Every substantive statement is grounded in the
   profile files read in Step 1.
6. **Respect the volume guardrails.** Caps and the two-silent-touch close-out in Step 6
   are enforced before every new first touch, not just mentioned.
