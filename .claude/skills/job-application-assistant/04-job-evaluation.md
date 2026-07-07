# Job Evaluation Framework

<!-- SETUP: Skill match areas and career goals are personalized by running /setup -->

## Scoring Dimensions

Evaluate each job posting against these five dimensions:

### 1. Technical Skills Match (0-100)
How well do the required/preferred skills align with the candidate's capabilities?

| Score | Meaning |
|-------|---------|
| 80-100 | Core requirements are primary skills |
| 60-79 | Most requirements match, 1-2 gaps that are learnable |
| 40-59 | Partial match, significant upskilling needed |
| 0-39 | Fundamental mismatch |

**Strong match areas:** AI workflow integration & enablement, AI adoption / change management, full-stack web app building (JavaScript, HTML/CSS), business operations & process improvement, cross-functional stakeholder alignment, daily hands-on use of Claude / Claude Code / Gemini / ChatGPT
**Moderate match areas:** Product/technical PM work, data visualization, requirements gathering, Google Apps Script automation, Spanish-language client work
**Weak match areas:** Formal software engineering (algorithms, data structures, systems design at scale), backend/database engineering, ML/model training, quota-carrying sales, roles requiring 5+ years or a CS degree

### 2. Experience Match (0-100)
Does work history align with what they're looking for?

| Score | Meaning |
|-------|---------|
| 80-100 | Direct experience in the same domain and role type |
| 60-79 | Related experience, transferable skills clear |
| 40-59 | Adjacent experience, would need to make the case |
| 0-39 | Unrelated experience |

**Strong:** AI Strategist / AI adoption & enablement, business operations analysis, building internal tools for non-technical orgs, AI consulting (Theron Digital)
**Moderate:** Forward-Deployed / Solutions Engineer (real shipped full-stack apps, but not from an engineering-org background), Founder's Associate (generalist range across ops/build/GTM), Technical/Product PM
**Entry-level:** Anything requiring 5+ years, formal SWE experience, or people-management history — Michael is ~2 years into his post-grad career

### 3. Behavioral/Culture Fit (0-100)
Does the role and company culture match the behavioral profile?

| Score | Meaning |
|-------|---------|
| 80-100 | Culture strongly matches behavioral preferences |
| 60-79 | Mixed signals but mostly compatible |
| 40-59 | Some friction areas |
| 0-39 | Significant culture mismatch |

**Red flags to research:** Department disorganization, work dominated by maintenance over development, poor chemistry with leadership, culture mismatches. Check reviews, media coverage, LinkedIn connections, and network contacts for insider perspective.

### 4. Location & Logistics (Pass/Fail + Notes)
Michael is **relocation-friendly** and actually prefers to relocate. Geography is a wide net, not a filter.
- Remote (US): PASS
- On-site/hybrid in SoCal (Orange County / LA): PASS (current base)
- Requires US relocation: PASS
- English-speaking Europe (remote or relocation): PASS — but FLAG work-authorization / visa sponsorship (US citizen; will need sponsorship for EU roles) and timezone overlap for remote
- Non-English-primary work environment: FLAG (Spanish OK; other languages a barrier)

### 5. Career Alignment & Motivation (0-100)
Does this role advance career goals and contain tasks that energize?

| Score | Meaning |
|-------|---------|
| 80-100 | Strongly aligned with career direction, clear growth path |
| 60-79 | Good role but only partially aligned with long-term goals |
| 40-59 | Decent job but doesn't build toward career goals |
| 0-39 | Dead end or backwards step |

**Career goals:**
- Land a role at the AI frontier — an AI-native startup or AI lab where he works with the latest models and tooling daily
- Maximize scope and ownership; keep building things end-to-end rather than owning a narrow slice
- Accelerate compensation and seniority trajectory over the next few years

**Motivation filter:** Evaluate not just whether Michael *can* do the tasks, but whether they will *energize* him. Consider:
- Tasks that energize: building/shipping working software, standing up something 0-to-1, driving AI adoption, working directly with customers/stakeholders, high-autonomy problem-solving
- Tasks that drain: quota-carrying cold-call sales, narrow maintenance of a large existing codebase, heavy process/approval overhead, purely administrative work
- Non-task factors: high autonomy, direct impact, closeness to frontier AI, strong growth path

**Life situation alignment:** Consider personal constraints:
- **Security**: Currently employed and running a consulting practice — can be selective; ~$100K USD base is the floor to flag under-market
- **Flexibility**: Relocation-friendly (US and English-speaking Europe); prefers to relocate
- **Professional development**: Wants to compound technical + AI + business range fast; values environments that stretch scope

### 6. Salary Benchmark (Optional)

If the salary lookup tool is configured (`salary_data.json` exists), look up the company:
```
python salary_lookup.py "<Company Name>" --json
```

If a city is known from the posting, add `--city "<City>"` to narrow results.

Present findings as:
```
### Salary Benchmark
| Metric | Value |
|--------|-------|
| [Category] index | XX.X (+/-X.X% vs baseline) |
| Overall index | XX.X (+/-X.X% vs baseline) |
```

Interpret results relative to the baseline defined in the data file's metadata. For index-based data, higher typically means above-market compensation.

If the salary tool is not configured, skip this section.

## Output Format

Present the evaluation as:

```
## Job Fit Evaluation: [Role] at [Company]

| Dimension | Score | Notes |
|-----------|-------|-------|
| Technical Skills | XX/100 | [brief note] |
| Experience Match | XX/100 | [brief note] |
| Behavioral Fit | XX/100 | [brief note] |
| Location | PASS/FAIL | [brief note] |
| Career Alignment | XX/100 | [brief note] |

**Overall Score: XX/100** (weighted average of scored dimensions)

### Verdict: [Strong Fit / Good Fit / Moderate Fit / Weak Fit / Poor Fit]

### Key Strengths for This Role
- [bullet points]

### Gaps to Address
- [bullet points]

### Recommendation
[1-2 sentences: apply/skip/apply with caveats]

### Company Research Checklist
- [ ] Checked company website (mission, values, recent news)
- [ ] Checked review sites (Glassdoor, Jobindex, etc.)
- [ ] Checked LinkedIn for team size, recent hires, connections
- [ ] Checked media for restructuring, growth, or workplace issues
- [ ] Identified network contacts who may know the team/manager
```

## Weighting
- Technical Skills: 30%
- Experience Match: 25%
- Behavioral Fit: 15%
- Career Alignment: 30%

(Location is pass/fail, not weighted)

## Thresholds
- **Strong Fit** (75+): Definitely apply, tailor everything
- **Good Fit** (60-74): Apply, address gaps in cover letter
- **Moderate Fit** (45-59): Consider carefully, discuss with user
- **Weak Fit** (30-44): Probably skip unless strategic reasons
- **Poor Fit** (<30): Skip

## Pre-Application: Call the Employer (Best Practice)

Before writing the application, consider whether the candidate should call the contact person listed in the posting. **Only call if there are substantive questions** - never call just to "be remembered."

### When to Suggest Calling
- The posting has unclear or ambiguous requirements
- It's unclear which competencies are essential vs. nice-to-have
- The role description is vague about day-to-day tasks
- There's a named contact person who invites questions

### Good Questions to Ask
- "What are the primary challenges in this role?"
- "How is time typically divided across the listed responsibilities?"
- "Which competencies are most critical for success in this position?"
- "What does success look like in the first 6-12 months?"

### Rules for the Call
- Prepare a 30-second "elevator pitch" about your background in case they ask
- The call's purpose is **gathering information**, not delivering a pitch
- Take notes - use what you learn to tailor the application
- Reference the conversation naturally in the cover letter ("After speaking with [name], I was especially drawn to...")
